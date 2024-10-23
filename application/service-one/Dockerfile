# Build stage
FROM maven:3.8-jdk-8 AS builder

WORKDIR /app
COPY pom.xml .
COPY src ./src

# Run maven build
RUN mvn clean package

FROM openjdk:8-jre

# environment
EXPOSE 8082

# executable
COPY --from=builder /app/target/api-gateway.jar app.jar

# run app as user 'booter'
RUN touch /app.jar

ENTRYPOINT ["java", "-Xmx256m", "-Xss32m", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]
