FROM docker.elastic.co/logstash/logstash-oss:7.10.1

# Add your logstash plugins setup here
# Example: RUN logstash-plugin install logstash-filter-json

USER root
RUN echo "root:admin" | chpasswd

USER logstash
RUN logstash-plugin install logstash-filter-json
RUN logstash-plugin install logstash-input-tcp
RUN logstash-plugin install logstash-input-udp


EXPOSE 5044
# https://discuss.elastic.co/t/logstash-ports-5044-9600-and-9700/165096