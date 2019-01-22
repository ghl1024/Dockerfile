#Base Image
FROM runtime/tomcat

#Maintainer
MAINTAINER shundong.zhao shundong.zhao@linuxhot.com

ADD jenkins.war /usr/local/tomcat/webapps/

#Outside port
EXPOSE 22 8080

CMD ["/usr/bin/supervisord","-c","/etc/supervisord.conf"]
