FROM ubuntu:20.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && \
    apt-get install -y openjdk-11-jdk maven tomcat9 git
RUN git clone https://github.com/cloud-dev-user/java-war-project.git /tmp/java-war-project
RUN cd /tmp/java-war-project && \
    mvn package
RUN cp /tmp/java-war-project/target/*.war /var/lib/tomcat9/webapps/demo.war
ENV CATALINA_HOME=/usr/share/tomcat9
ENV CATALINA_BASE=/var/lib/tomcat9
ENV PATH=$CATALINA_HOME/bin:$PATH
EXPOSE 8080
CMD ["/usr/share/tomcat9/bin/catalina.sh", "run"]