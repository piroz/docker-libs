FROM centos:6

RUN yum -y install mysql-server

ADD setup.sql /tmp
RUN echo "NETWORKING=yes" > /etc/sysconfig/network
RUN service mysqld start && sleep 10 && mysql < /tmp/setup.sql
EXPOSE 3306
CMD ["/usr/bin/mysqld_safe"]
