FROM docker.elastic.co/beats/metricbeat-oss:7.10.1

USER root

RUN echo "root:admin" | chpasswd

USER metricbeat
