FROM nginx:1.18.0

ADD default.conf /etc/nginx/conf.d/default.conf
ADD nginx.conf /etc/nginx/nginx.conf

RUN apt-get update && \
    apt-get install -y --no-install-recommends openssh-server rsyslog && \
    apt-get clean && \
    rm -rf /tmp/* /var/lib/apt/lists/* /var/tmp/*

RUN echo "root:admin" | chpasswd && \
    mkdir -p /var/run/sshd && \
    mkdir -p /root/.ssh && \
    sed -i 's/^\(UsePAM\|UseDNS\)/#\1/' /etc/ssh/sshd_config && \
    echo "" >>/etc/ssh/sshd_config && \
    echo "UsePAM no" >>/etc/ssh/sshd_config && \
    echo "UseDNS no" >>/etc/ssh/sshd_config && \
    sed -i "s/#PermitRootLogin.*/PermitRootLogin yes/1" /etc/ssh/sshd_config

#EXPOSE 22
EXPOSE 80

CMD service rsyslog start && \
    service ssh start && \
    nginx -g "daemon off;"
