FROM ubuntu:20.04
RUN apt update
RUN apt install -y default-jdk maven tomcat9 git
RUN git clone https://github.com/cloud-dev-user/java-war-project.git /tmp/java-war-project
RUN cd /tmp/java-war-project
RUN mvn package
RUN cp /tmp/java-war-project/target/*.war /var/lib/tomcat9/webapps/demo.war
EXPOSE 8080
CMD ["systemctl", "start", "tomcat9"]