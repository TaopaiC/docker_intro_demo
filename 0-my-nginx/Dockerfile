# simple nginx image
# docker build -t my-nginx .
# docker run --rm -v `pwd`:/usr/share/nginx/html my-nginx
FROM ubuntu:14.04

RUN apt-get update && apt-get upgrade -y && apt-get install -y nginx && apt-get clean
RUN sed -i "s/access_log.*;/access_log \/dev\/stdout;/g;s/error_log.*;/error_log \/dev\/stdout;/g" /etc/nginx/nginx.conf
RUN echo 'daemon off;' >> /etc/nginx/nginx.conf
WORKDIR /usr/share/nginx/html
EXPOSE 80
CMD ["nginx"]
