FROM debian:9

ARG WP_FILE=latest.tar.gz

WORKDIR /tmp
#ADD https://wordpress.org/${WP_FILE} .

RUN apt-get -y update
RUN apt-get install -y apache2 wget libapache2-mod-php7.0 php-mysql php-gd php-redis
RUN wget --no-check-certificate https://wordpress.org/${WP_FILE}
RUN tar xf ${WP_FILE}
#RUN mkdir -p /var/www/html
RUN mv wordpress/* /var/www/html
RUN rm ${WP_FILE}
RUN apt-get clean

#    apt-get install -y apache2 libapache2-mod-php7.0 php-mysql php-gd php-redis && \

EXPOSE 80

ENTRYPOINT ["/usr/sbin/apache2ctl", "-DFOREGROUND"]
