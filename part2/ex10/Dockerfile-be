FROM node:latest
COPY . ./
RUN npm install 
ENV FRONT_URL http://localhost:5000
CMD ["npm", "start"]
EXPOSE 8000
