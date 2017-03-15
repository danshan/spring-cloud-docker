FROM maven:3.3.9-jdk-8
MAINTAINER Dan <i@shanhh.com>

RUN mkdir -p /opt/data
RUN useradd eureka -m

ADD . /opt/data/spring-cloud-eureka
RUN chown -R eureka /opt/data/spring-cloud-eureka

USER erueka

WORKDIR /opt/data/spring-cloud-eureka
RUN mvn clean package

EXPOSE 8761

ENTRYPOINT ["/opt/data/spring-cloud-eureka/bin/entrypoint.sh"]
