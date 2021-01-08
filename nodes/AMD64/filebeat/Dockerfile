FROM docker.elastic.co/beats/filebeat-oss:7.10.1

USER root

RUN yum install -y net-tools nc nano && \
    yum clean all && \
    echo "root:admin" | chpasswd

COPY --chown=root:filebeat filebeat.yml /usr/share/filebeat/filebeat.yml

RUN chmod 644 /usr/share/filebeat/filebeat.yml
