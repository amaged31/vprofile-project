FROM mysql:8.3.0 
LABEL "Project"="Vprofile"
LABEL "Author"="AmirMaged"

FROM tomcat:10.1.23-jdk21-temurin-jammy

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"


ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
