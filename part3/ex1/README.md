Before Optimization:

Frontend:
 
    Size: 1.12GB

    Dockerfile:
    FROM node:latest
    COPY . ./
    RUN npm install 
    RUN npm install -g serve
    RUN npm run build
    ENV API_URL http://localhost:8000
    CMD ["npm", "start"]
    EXPOSE 5000

Backend: 

    Size: 997MB

    Dockerfile:
    FROM node:latest
    COPY . ./
    RUN npm install 
    ENV FRONT_URL http://localhost:5000
    CMD ["npm", "start"]
    EXPOSE 8000


After Optimization:

Frontend:

    Size:603MB

    Dockerfile:
    FROM ubuntu:latest
    WORKDIR /app
    COPY . ./
    RUN apt-get update && apt-get install -y nodejs && \
        apt-get install -y npm && \
        npm install && \
        npm install -g serve && \
        npm run build && \
        rm -rf /var/lib/apt/lists/* 
    ENV API_URL http://localhost:8000
    CMD ["npm", "start"]
    EXPOSE 5000

Backend:

    Size:447MB

    Dockerfile:
    FROM ubuntu:latest
    COPY . ./
    RUN apt-get update && apt-get install -y nodejs && \
        apt-get install -y npm && \
        npm install && \
        rm -rf /var/lib/apt/lists/*
    ENV FRONT_URL http://localhost:5000
    CMD ["npm", "start"]
    EXPOSE 8000
