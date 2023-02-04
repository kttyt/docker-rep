FROM httpd:2-bullseye

RUN apt-get update && apt-get -y install libapache2-mod-perl2 && apt-get clean
RUN echo admin | htpasswd -i -c /usr/local/apache2/.htpasswd admin
RUN ln -s /usr/lib/apache2/modules/mod_perl.so /usr/local/apache2/modules/mod_perl.so
COPY ConvertUsrToLowercase.pm /etc/perl/MyApache2/
COPY --chown=root:www-data httpd.conf /usr/local/apache2/conf/

