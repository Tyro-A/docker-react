FROM node:14.14.0-alpine AS builder
WORKDIR "/app"
COPY ./package.json ./
RUN npm install
COPY . .
RUN nmp run build

FROM nginx
EXPOSE 3000
COPY ./nginx/defualt.conf /etc/nginx/conf.d/defualt.conf
COPY --from=builder /app/build /usr/share/nginx/html