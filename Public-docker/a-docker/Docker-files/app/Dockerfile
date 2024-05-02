FROM openjdk:23-jdk AS BUILD_IMAGE 
RUN apt update && install maven -y

RUN git clone https://github.com/devopshydclub/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

FROM tomcat:10.1.23-jdk21-temurin-jammy
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE target/vprofile-v2.war /C:/Users/ammaged/vproject/vprofile-project/


LABEL "Project"="Vprofile"
LABEL "Author"="AmirMaged"

EXPOSE 8080
CMD ["catalina.sh", "run"]
WORKDIR /usr/local/tomcat/
VOLUME /usr/local/tomcat/webapps