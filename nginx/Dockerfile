FROM nginx:stable-alpine
ARG domain

RUN apk update && apk add openssl

RUN mkdir -p /etc/ssl/private /etc/ssl/certs && \
    openssl req -x509 -nodes -days 365 \
    -subj "/C=US/ST=NC/O=UNION/CN=${domain}" \
    -addext "subjectAltName=DNS:${domain}" \
    -newkey rsa:2048 \
    -keyout /etc/ssl/private/${domain}-selfsigned.key \
    -out /etc/ssl/certs/${domain}-selfsigned.crt