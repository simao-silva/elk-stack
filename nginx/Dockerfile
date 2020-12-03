FROM nginx:stable

ADD default.conf /etc/nginx/conf.d/default.conf
ADD nginx.conf /etc/nginx/nginx.conf

RUN echo "127.0.0.1	kibana.secop.edu\n127.0.0.1	elastic.secop.edu" >> /etc/hosts

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

