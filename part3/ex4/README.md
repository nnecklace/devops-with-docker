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
    Size:296MB
    Dockerfile:
    FROM node:alpine
    COPY . ./
    RUN npm install 
    RUN npm install -g serve
    RUN npm run build
    ENV API_URL http://localhost:8000
    CMD ["npm", "start"]
    EXPOSE 5000

Backend:
    Size:176MB
    Dockerfile:
    FROM node:alpine
    COPY . ./
    RUN npm install 
    ENV FRONT_URL http://localhost:5000
    CMD ["npm", "start"]
    EXPOSE 8000

