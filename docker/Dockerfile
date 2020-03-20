FROM richarvey/nginx-php-fpm:1.8.2

RUN docker-php-ext-install -j$(nproc) bcmath sockets

CMD ["/start.sh"]
