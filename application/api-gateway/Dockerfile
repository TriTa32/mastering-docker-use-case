FROM openjdk:8-jre-alpine
# environment
EXPOSE 8080
# executable ADD @project.artifactId@-@project.version@.jar app.jar
COPY target/api-gateway.jar app.jar
# run app as user 'booter'
RUN touch /app.jar
ENTRYPOINT ["java", "-Xmx256m", "-Xss32m", "-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]
    