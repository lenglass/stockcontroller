FROM alpine:3.8

ENV TOMCAT_MAJOR=9 \
    TOMCAT_VERSION=9.0.12 \
    TOMCAT_HOME=/opt/tomcat \
    CATALINA_HOME=/opt/tomcat \
    CATALINA_OUT=/dev/null \
    MYSQL_JDBC_VERSION=8.0.13

RUN mkdir -p /opt && \
    apk upgrade --update && \
    apk add --update openjdk8-jre curl && \
    curl -jksSL -o /tmp/apache-tomcat.tar.gz http://archive.apache.org/dist/tomcat/tomcat-${TOMCAT_MAJOR}/v${TOMCAT_VERSION}/bin/apache-tomcat-${TOMCAT_VERSION}.tar.gz && \
    tar -C /opt -xvzf /tmp/apache-tomcat.tar.gz && \
    ln -s /opt/apache-tomcat-${TOMCAT_VERSION} ${TOMCAT_HOME} && \
    rm -rf ${TOMCAT_HOME}/webapps/* && \
    curl -jksSL -o /tmp/mysql-connector-java.tar.gz http://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-${MYSQL_JDBC_VERSION}.tar.gz && \
    tar -C /tmp -xvzf /tmp/mysql-connector-java.tar.gz && \
    cp /tmp/mysql-connector-java-${MYSQL_JDBC_VERSION}/mysql-connector-java-${MYSQL_JDBC_VERSION}.jar /opt/tomcat/lib/ && \
    apk del curl && \
    rm -rf /tmp/* /var/cache/apk/*

EXPOSE 8080
ENTRYPOINT [ "/opt/tomcat/bin/catalina.sh", "run" ]