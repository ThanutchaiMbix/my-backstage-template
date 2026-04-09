FROM maven:3.9-eclipse-temurin-17 AS builder
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:17-jdk-slim
WORKDIR /app
COPY target/${{ values.application_name }}.jar app.jar
ENTRYPOINT ["java","-jar","/app/app.jar"]