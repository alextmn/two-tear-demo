# Maven build container 

FROM maven:3.6.3-openjdk-11 AS maven_build

COPY springboot/pom.xml /tmp/

COPY springboot/src /tmp/src/

WORKDIR /tmp/

RUN mvn package

#pull base image

FROM openjdk

#maintainer 
MAINTAINER alex.shpurov@route1.com

#expose port 8080
#EXPOSE 8080

#default command
CMD java -jar -Dserver.port=9090 /data/hello-world-0.1.0.jar

#copy hello world to docker image from builder image

COPY --from=maven_build /tmp/target/hello-world-0.1.0.jar /data/hello-world-0.1.0.jar
