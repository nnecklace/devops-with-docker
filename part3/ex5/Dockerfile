FROM node:latest as node
COPY . ./
RUN npm install 
RUN npm run build

FROM nginx:latest
COPY --from=node /dist /usr/share/nginx/html
EXPOSE 80
