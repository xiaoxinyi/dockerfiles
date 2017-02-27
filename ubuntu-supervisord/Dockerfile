FROM ubuntu:16.04
MAINTAINER examples@docker.com

COPY resolv.conf /etc/resolv.conf
COPY sources.list /etc/apt/sources.list

RUN apt-get update && apt-get install -y openssh-server apache2 supervisor
RUN mkdir -p /var/lock/apache2 /var/run/apache2 /var/run/sshd /var/log/supervisor

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 22 80
CMD ["/usr/bin/supervisord"]