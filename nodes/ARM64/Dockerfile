FROM debian:10-slim

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
    apt-get install -y --no-install-recommends wget netcat && \
    apt-get clean && \
    rm -rf /tmp/* /var/lib/apt/lists/* /var/tmp/*

RUN wget https://artifacts.elastic.co/downloads/beats/filebeat/filebeat-7.10.1-arm64.deb && \
    dpkg -i filebeat-7.10.1-arm64.deb

COPY filebeat.yml /etc/filebeat/filebeat.yml

CMD echo "Starting...\n" && \
    /usr/share/filebeat/bin/filebeat -c /etc/filebeat/filebeat.yml --path.home /usr/share/filebeat --path.config /etc/filebeat --path.data /var/lib/filebeat --path.logs /var/log/filebeat
