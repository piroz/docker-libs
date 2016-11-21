FROM centos:6

RUN yum -y install mysql-server

ADD setup.sql /tmp
RUN echo "NETWORKING=yes" > /etc/sysconfig/network
EXPOSE 3306
RUN chkconfig mysqld on
ENTRYPOINT /etc/init.d/mysqld start && sleep 10 && cat /tmp/setup.sql | mysql && /bin/bash
