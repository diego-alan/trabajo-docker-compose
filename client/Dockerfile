FROM node:16 as build-step
RUN mkdir -p /app
WORKDIR /app
COPY package.json /app
RUN npm install
COPY . /app
RUN npm run build


FROM nginx:1.20.1
COPY --from=build-step /app/dist /usr/share/nginx/html
EXPOSE 8083:80