#Base Image
FROM system/centos

#Maintainer
MAINTAINER GuoHaiLiang

#Run
RUN yum install -y java-1.8.0-openjdk java-1.8.0-openjdk-devel && yum clean all
ENV JAVA_HOME /usr/lib/jvm/java-1.8.0-openjdk

#Tomcat
ADD apache-tomcat-8.5.32.tar.gz /usr/local
RUN ln -s /usr/local/apache-tomcat-8.5.32 /usr/local/tomcat

#For Supervisor
ADD tomcat.ini /etc/supervisord.d/tomcat.ini
ENV TOMCAT_HOME /usr/local/tomcat

#Outside port
EXPOSE 22 8080

CMD ["/usr/bin/supervisord","-c","/etc/supervisord.conf"]
