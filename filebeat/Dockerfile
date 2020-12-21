FROM docker.elastic.co/beats/filebeat-oss:7.10.1
USER root

RUN yum install -y net-tools nc nano && \
    yum clean all && \
    echo "root:admin" | chpasswd

COPY config/filebeat.yml /usr/share/filebeat/filebeat.yml
#COPY modules.d/system.yml /usr/share/filebeat/modules.d/system.yml
RUN chown root:filebeat /usr/share/filebeat/filebeat.yml
#&& \
#    filebeat modules enable system && \
#    filebeat setup

#USER filebeat
