FROM mariadb:10.6

RUN apt -y update && apt -y upgrade
RUN apt -y install curl
RUN apt -y install rpm
RUN apt -y install alien
RUN curl -L -O https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-8.7.0-x86_64.rpm
RUN alien -i filebeat-8.7.0-x86_64.rpm
RUN filebeat modules enable mysql
RUN touch /var/log/mysql/mariadb-slow.log
RUN chown mysql:mysql /var/log/mysql/mariadb-slow.log