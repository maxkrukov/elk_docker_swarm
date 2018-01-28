FROM nginx:latest

RUN apt-get update && apt-get install -y openssl
RUN mkdir /etc/nginx/ssl
RUN openssl req -x509 -nodes   -days 36000 -newkey rsa:2048 \
       -subj "/C=NX/O=nginx/OU=Domain Control Validated/CN=*.nginx.proxy" \
       -keyout /etc/nginx/ssl/nginx.key -out /etc/nginx/ssl/nginx.crt
RUN openssl dhparam -out /etc/nginx/ssl/dhparam.pem 128

CMD ["/bin/bash", "-c", "nginx -g 'daemon off;'"]
