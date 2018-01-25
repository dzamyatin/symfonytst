FROM debian:jessie
MAINTAINER Daniil <zamyatin.daniil@gmail.com>

VOLUME ["/var/www"]

RUN apt-get update && \
    apt-get install -y \
      apt-utils \
      php5 \
      php5-dev \
      libapache2-mod-php5 \
      php5-gd \
      php5-json \
      php5-ldap \
      php5-mysql \
      php5-pgsql

RUN apt-get install -y \
      git \
      python \
      python-setuptools && \
      easy_install pip && \
      pip install pyyaml	

RUN cd ~ && \
 git clone https://github.com/tarantool/tarantool-php.git && \
 cd tarantool-php && \
 phpize && \
 ./configure && \
 make && \
 make install

EXPOSE 80
CMD ["/bin/sh","-c","while true; do echo hello world; sleep 1; done"]
