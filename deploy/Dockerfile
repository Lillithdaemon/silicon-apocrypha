FROM klakegg/hugo:0.131 AS builder

WORKDIR /src
COPY . .
RUN hugo --minify --gc

FROM nginx:1.29-alpine
COPY --from=builder /src/public /usr/share/nginx/html
EXPOSE 8080
