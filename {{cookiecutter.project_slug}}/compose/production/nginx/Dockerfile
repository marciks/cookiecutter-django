
FROM nginx:stable-alpine

COPY nginx.conf /etc/nginx/nginx.conf
COPY service-django.conf /etc/nginx/service-django.conf

ADD entrypoint.sh /entrypoint.sh
ADD le.sh /le.sh

RUN \
 rm /etc/nginx/conf.d/default.conf && \
 chmod +x /entrypoint.sh && \
 chmod +x /le.sh && \
 apk add  --update certbot tzdata openssl && \
 rm -rf /var/cache/apk/*

CMD ["/entrypoint.sh"]
