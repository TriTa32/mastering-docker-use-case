FROM openjdk:8-jre

# environment
EXPOSE 8084

# executable
COPY target/service-two.jar app.jar

# run app as user 'booter'
RUN touch /app.jar

ENTRYPOINT ["java", "-Xmx256m", "-Xss32m", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]
