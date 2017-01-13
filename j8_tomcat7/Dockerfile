FROM cheempz/java_base:java8

RUN apt-get update && apt-get install -y curl unzip \
    && rm -rf /var/lib/apt/lists/*

# create two tomcat installs
# NOTE revisit this, containerize the supporting tomcat2 server?
WORKDIR /opt
RUN curl -LO https://s3.amazonaws.com/apm-qa-automation/java/tomcat/apache-tomcat-7.0.41.zip \
    && unzip -q -u -o apache-tomcat-7.0.41.zip
    && mv apache-tomcat-7.0.41 apache-tomcat-7.0.41_2 \
    && ln -s /opt/apache-tomcat-7.0.41_2 /opt/tomcat2 \
    && unzip -q -u -o apache-tomcat-7.0.41.zip \
    && ln -s /opt/apache-tomcat-7.0.41 /opt/tomcat \
    && chmod 755 tomcat/bin/* \
    && chmod 755 tomcat2/bin/* \
    && rm /opt/apache-tomcat-7.0.41.zip

ENV CATALINA_HOME=/opt/tomcat
