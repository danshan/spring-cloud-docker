FROM maven:3.3.9-jdk-8
MAINTAINER Dan <i@shanhh.com>

ENV APP_USER eureka
ENV DATA_DIR /opt/data
ENV APP_NAME eureka

RUN mkdir -p ${DATA_DIR}
RUN useradd ${APP_USER} -m

ADD . ${DATA_DIR}/${APP_NAME}
RUN chown -R ${APP_USER} ${DATA_DIR}

USER ${APP_USER}

WORKDIR ${DATA_DIR}/${APP_NAME}
RUN mvn clean package

EXPOSE 8761

ENTRYPOINT ["$DATA_DIR/$APP_NAME/bin/entrypoint.sh"]
