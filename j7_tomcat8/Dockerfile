FROM cheempz/java_base:java7

ARG tomcat_version=8.5.9
ENV CATALINA_HOME=/opt/tomcat
ENV PATH=${CATALINA_HOME}/bin:$PATH

WORKDIR $CATALINA_HOME

ADD https://www.apache.org/dyn/closer.cgi?action=download&filename=tomcat/tomcat-8/v${tomcat_version}/bin/apache-tomcat-${tomcat_version}.tar.gz tomcat.tar.gz

RUN tar -xzf tomcat.tar.gz --strip-components=1 && rm tomcat.tar.gz*

EXPOSE 8080
CMD ["catalina.sh", "run"]