FROM nginx:1.15

RUN rm -f /etc/localtime && ln -s /usr/share/zoneinfo/America/Sao_Paulo /etc/localtime

COPY site/ /usr/share/nginx/html/

ENV NGIX_HOME /usr/share/nginx/html

RUN apt-get update && \
  apt-get install -y iputils-ping && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /etc/apt/sources.list.d/*

EXPOSE 80 443

WORKDIR /tmp

VOLUME [ "/data" ]

CMD nginx -g 'daemon off;'
