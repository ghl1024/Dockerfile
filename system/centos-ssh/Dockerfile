#Base Image
FROM centos

#Maintainer
MAINTAINER shundong.zhao shundong.zhao@linuxhot.com

#Run
RUN rpm -ivh https://mirrors.aliyun.com/epel/epel-release-latest-7.noarch.rpm
RUN yum install -y wget sudo git tree net-tools supervisor openssh-clients openssh-server openssl-devel && yum clean all
RUN ssh-keygen -t rsa -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key
RUN ssh-keygen -A -t dsa -f /etc/ssh/ssh_host_dsa_key

#Set root password
RUN echo "root:devopsedu.com" | chpasswd

#For Supervisor
ADD supervisord.conf /etc/supervisord.conf
ADD sshd.ini /etc/supervisord.d/sshd.ini

#Outside port
EXPOSE 22

CMD ["/usr/bin/supervisord","-c","/etc/supervisord.conf"]
