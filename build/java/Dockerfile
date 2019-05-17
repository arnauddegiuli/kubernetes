FROM arm32v6/maven:3.6.1-jdk-8-alpine
COPY tmp/qemu-arm-static /usr/bin/qemu-arm-static

WORKDIR /usr/local/src
COPY . .
RUN mvn clean package
 
# Final runtime image
FROM openjdk:8-jre-alpine as Final
WORKDIR /opt
COPY --from=Build /usr/local/src/notification-rest-api/target/*.jar ./ 

EXPOSE 8087
EXPOSE 8089
ENTRYPOINT ["java", "-jar", "notification-rest-api-0.0.1-SNAPSHOT.jar", "-Duser.dir=/tmp"]

