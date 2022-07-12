#FROM adoptopenjdk/openjdk:17-alpine
FROM bellsoft/liberica-openjdk-alpine:latest
RUN apk add -U tzdata
ENV TZ America/Lima
RUN ln -snf /usr/share/zoneinfo/${TZ} /etc/localtime
RUN echo "${TZ}" > /etc/timezone
VOLUME /tmp
EXPOSE 8761
ADD ./target/config-service-0.1.jar config.jar
ENTRYPOINT ["java", "-jar", "/config.jar"]