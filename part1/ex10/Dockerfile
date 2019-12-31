FROM node:latest
COPY . ./
RUN npm install 
RUN npm install -g serve
RUN npm run build
ENV API_URL http://localhost:8000
CMD ["npm", "start"]
EXPOSE 5000
