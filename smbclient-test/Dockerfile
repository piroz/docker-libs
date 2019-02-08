FROM debian:stretch

RUN apt-get update && \
    apt-get install -y && \
    apt-get install smbclient cifs-utils netcat nmap vim -y && \
    apt-get clean

RUN mkdir /data
WORKDIR /data

CMD bash