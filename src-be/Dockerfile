# FROM maven:3.8-openjdk-11 as builder
#
# WORKDIR /build
#
# COPY mvnw .
# COPY .mvn .mvn
# COPY pom.xml .
#
# RUN chmod +x ./mvnw
# RUN ./mvnw dependency:go-offline -B
#
# COPY /src ./src
#
# RUN ./mvnw deploy
#
# FROM openjdk:11.0-jre
#
# WORKDIR /root/
# COPY --from=0 /build/target/ToDoApplication.jar ToDoApplication.jar
#
# ENTRYPOINT ["java", "-jar", "/root/ToDoApplication.jar"]

FROM adoptopenjdk:11-jre-hotspot

# RUN addgroup -S spring && adduser -S spring -G spring

# USER spring:spring

ARG JAR_FILE=*.jar

COPY ${JAR_FILE} app.jar

ENTRYPOINT ["java","-jar","/app.jar"]