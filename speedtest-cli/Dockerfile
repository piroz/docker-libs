FROM python:3.7.2-alpine

RUN pip install speedtest-cli

ENTRYPOINT [ "speedtest-cli" ]

CMD [ "--json" ]