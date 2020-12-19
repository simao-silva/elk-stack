FROM docker.elastic.co/beats/filebeat-oss:7.10.1 AS base
USER root

# Fix systemd (https://unix.stackexchange.com/a/490783)
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
    rm -f /lib/systemd/system/multi-user.target.wants/*; \
    rm -f /etc/systemd/system/*.wants/*; \
    rm -f /lib/systemd/system/local-fs.target.wants/*; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
    rm -f /lib/systemd/system/basic.target.wants/*; \
    rm -f /lib/systemd/system/anaconda.target.wants/*;

VOLUME [ "/sys/fs/cgroup" ]
CMD ["/usr/sbin/init"]

#RUN filebeat modules enable elasticsearch && \
#    filebeat setup && \
#    filebeat -e

FROM base
USER root
RUN yum install -y openssh-server net-tools nc nano rsyslog && \
    yum clean all && \
    echo "root:admin" | chpasswd
EXPOSE 22
ENTRYPOINT ["/usr/sbin/init"]
CMD systemctl start rsyslog && \
    systemctl start sshd
