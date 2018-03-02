FROM debian:jessie

RUN apt-get update
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y exim4-daemon-light mailutils
RUN sed -i -e "s/^dc_eximconfig_configtype=.\+/dc_eximconfig_configtype=\'internet\'/g" /etc/exim4/update-exim4.conf.conf
RUN sed -i -e "s/^dc_local_interfaces=.\+/dc_local_interfaces=\'127.0.0.1\'/g" /etc/exim4/update-exim4.conf.conf
EXPOSE 25

ENV TINI_VERSION v0.16.1
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini
ENTRYPOINT ["/tini", "--"]

CMD ["exim", "-v"]
