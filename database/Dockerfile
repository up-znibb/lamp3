FROM mariadb:10.6

LABEL MAINTAINER="Emil Malm <emilamalm@gmail.com>"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get upgrade -y

#timezone
ENV TZ=Europe/Stockholm
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN touch /var/log/mysql/mysql-slow.log
RUN chown mysql:mysql /var/log/mysql/mysql-slow.log