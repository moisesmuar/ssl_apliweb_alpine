FROM httpd:2.4.51-alpine

    # copiar fichero de configuración a dir conf/ en container
COPY ./demo.apache.conf /usr/local/apache2/conf/

    # Escribir en fichero httpd.conf inclusión del fichero copiado
RUN echo "Include /usr/local/apache2/conf/demo.apache.conf" \
    >> /usr/local/apache2/conf/httpd.conf

RUN apk update \
    && apk --no-cache upgrade

# RUN apk add --upgrade certbot-apache

RUN apk add certbot
RUN apk add --upgrade certbot-apache
RUN apk add certbot-nginx

# instalar modulo apache2-ctl
RUN apk add apache2-ctl
# Alpine no tiene instalado rc-service 
RUN apk add openrc --no-cache
# https://certbot.eff.org/docs/contributing.html#plugin-architecture