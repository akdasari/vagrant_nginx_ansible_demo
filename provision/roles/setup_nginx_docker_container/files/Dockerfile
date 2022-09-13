FROM library/alpine:latest

MAINTAINER Anand Dasari  <gkdasari@gmail.com>

RUN apk add --update nginx && rm -rf /var/cache/apk/* && \
    touch /var/run/nginx.pid && \
    mkdir -p /var/lib/nginx/logs && \
    touch /var/lib/nginx/logs/error.log && \
    chown -R nobody:nobody /var/lib/nginx && \
    chown -R nobody:nobody /var/run/nginx.pid && \
    chown -R nobody:nobody /var/lib/nginx/logs/error.log && \
    chown -R nobody:nobody /var/log/nginx && \
    mkdir -p /var/tmp/nginx && \
    chown -R nobody:nobody /var/tmp/nginx/ 

COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./index.html /www/index.html

USER nobody

VOLUME /var/www

EXPOSE 8080

CMD ["nginx", "-g", "daemon off;"]


