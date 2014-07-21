# simple nginx image
# docker build -t my-nginx-onbuild .
# docker run --rm -v `pwd`:/usr/share/nginx/html my-nginx-onbuild
FROM ubuntu:14.04

RUN apt-get update && apt-get upgrade -y && apt-get install -y nginx && apt-get clean
RUN sed -i "s/access_log.*;/access_log \/dev\/stdout;/g;s/error_log.*;/error_log \/dev\/stdout;/g" /etc/nginx/nginx.conf
RUN echo 'daemon off;' >> /etc/nginx/nginx.conf
ONBUILD ADD . /usr/share/nginx/html
WORKDIR /usr/share/nginx/html
EXPOSE 80
ENTRYPOINT ["nginx"]
CMD [""]
