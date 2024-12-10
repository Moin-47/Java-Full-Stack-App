From node:22-alpine As nodejs

WORKDIR /app

COPY *.json ./

RUN npm install

COPY . .

RUN npm run build

FROM nginx:alpine

COPY --from=nodejs /app/build /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
