FROM ubuntu:14.04
ENV DEBIAN_FRONTEND noninteractive
ADD http://repo.zabbix.com/zabbix/2.4/ubuntu/pool/main/z/zabbix-release/zabbix-release_2.4-1+trusty_all.deb /zabbix-release.deb
RUN dpkg -i /zabbix-release.deb
RUN apt-get update -qq
RUN apt-get install -qy --no-install-recommends zabbix-frontend-php
RUN ln -sf /etc/zabbix/apache.conf /etc/apache2/conf-enabled/zabbix.conf
ADD php.ini /etc/php5/apache2/conf.d/30-zabbix.ini
ADD apache.conf /etc/apache2/conf-enabled/zabbix-server.conf
ADD run.sh /run.sh
CMD ["/run.sh"]
EXPOSE 80
