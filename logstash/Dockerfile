FROM docker.elastic.co/logstash/logstash-oss:7.10.1

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json

USER root
RUN echo "root:admin" | chpasswd

USER logstash
RUN logstash-plugin install logstash-filter-json && \
    logstash-plugin install logstash-input-tcp && \
    logstash-plugin install logstash-input-udp && \
    logstash-plugin install logstash-filter-grok

EXPOSE 5044
# https://discuss.elastic.co/t/logstash-ports-5044-9600-and-9700/165096