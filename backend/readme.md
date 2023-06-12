docker build --tag alexandre/mybackend .

docker run  --rm --name small_backend alexandre/mybackend

Question 1-2 Why do we need a multistage build? And explain each step of this dockerfile.
Answer1 So we have a standardized way of building our app that doesn't rely on the version of binaries, etc.  of our machine.

# Build 
# Specifying docker base image
FROM maven:3.8.6-amazoncorretto-17 AS myapp-build
#setting bash variable environment
ENV MYAPP_HOME /opt/myapp
#changing of directory
WORKDIR $MYAPP_HOME
#copying source files and maven configuration file into container
COPY pom.xml .
COPY src ./src
#running compilation command
RUN mvn package -DskipTests

# Run
FROM amazoncorretto:17
#specifying docker base image
ENV MYAPP_HOME /opt/myapp
#specifying an environment variable
WORKDIR $MYAPP_HOME
#changing of directory
COPY --from=myapp-build $MYAPP_HOME/target/*.jar $MYAPP_HOME/myapp.jar
#copying 
ENTRYPOINT java -jar myapp.jar
#command to be ran on docker start


