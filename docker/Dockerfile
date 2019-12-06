FROM amazonlinux:latest
MAINTAINER gaochuang@ukelink.com
WORKDIR /home
RUN yum -y install finger-server
RUN yum -y install unixODBC-devel
RUN yum -y install speex-devel
RUN yum -y install libedit-devel
RUN ln -sf /usr/lib64/libtinfo.so.6.0  /usr/lib64/libtinfo.so.5
RUN ln -sf /usr/lib64/libncurses.so.6.0  /usr/lib64/libncurses.so.5
RUN yum -y install procps
RUN yum -y install keepalived
RUN yum -y install initscripts
RUN mkdir /home/tss
#RUN yum -y install yum-utils
#RUN yum-config-manager --enable epel
#RUN yum install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
ADD freeswitch.tar.gz /home/tss/
RUN ln -sf /home/tss/freeswitch/bin/fs_start /usr/bin/
RUN ln -sf /home/tss/freeswitch/bin/freeswitch /usr/bin/
RUN ln -sf /home/tss/freeswitch/bin/fs_cli /usr/bin/
RUN yum -y install firewalld
RUN systemctl enable firewalld
#RUN systemctl start firewalld
#RUN firewall-cmd --zone=public --add-port=16384-32768/udp --permanent
#RUN firewall-cmd --add-port=5660/tcp --permanent
#RUN firewall-cmd --direct --permanent --add-rule ipv4 filter INPUT 0 --in-interface eth0 --destination 224.0.0.18 --protocol vrrp -j ACCEPT
#RUN firewall-cmd --reload

RUN systemctl enable keepalived
#RUN systemctl start keepalived
