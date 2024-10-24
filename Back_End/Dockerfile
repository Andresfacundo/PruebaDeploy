#FROM maven:3-eclipse-temurin-17 AS build
#COPY . .
#RUN mvn clean package -DskipTests
#
#FROM eclipse-temurin:17-alphine
#COPY --from=build /target/*.jar demo.jar
#EXPOSE 8080
#ENTRYPOINT ["java","-jar","demo.jar"]


FROM openjdk:17-jdk-alpine
WORKDIR /app
COPY . /app
RUN ./mvnw clean package
ARG JAR_FILE=target/*.jar
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar"]

