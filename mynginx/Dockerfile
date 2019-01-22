#Base Image
FROM centos

#Maintainer
MAINTAINER shundong.zhao shundong.zhao@linuxhot.com

#Run
RUN rpm -ivh https://mirrors.aliyun.com/epel/epel-release-latest-7.noarch.rpm
RUN yum install -y nginx --enablerepo=epel
RUN echo "daemone off;" >> /etc/nginx/nginx.conf
ADD index.html /usr/share/nginx/html/index.html
EXPOSE 80
CMD ["nginx"]
