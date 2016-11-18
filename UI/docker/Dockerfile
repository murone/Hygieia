
FROM docker.io/nginx:latest

MAINTAINER Hygieia@capitalone.com

RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
RUN apt-get install -y nodejs
RUN apt-get install -y npm
RUN ln -sf /usr/bin/nodejs /usr/bin/node

COPY default.conf /etc/nginx/conf.d/default.conf.templ
COPY conf-builder.sh /usr/bin/conf-builder.sh
COPY html /usr/share/nginx/html


EXPOSE 80 443

CMD conf-builder.sh &&\
  nginx -g "daemon off;"
