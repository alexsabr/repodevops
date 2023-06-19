

# Build
FROM maven:3.8.6-amazoncorretto-17 AS myapp-build
# Using image from amazon as build environment 
ENV MYAPP_HOME /opt/myapp
# setting a shell variable to be used

WORKDIR $MYAPP_HOME
# changing of working directory
COPY pom.xml .
# copying inside image maven config file
COPY src ./src
#copying source files
RUN mvn dependency:go-offline
# to speed up builds next times
RUN mvn package -DskipTests
# building app

# Run
FROM amazoncorretto:17
#using other image from amazon as run environment
ENV MYAPP_HOME /opt/myapp
WORKDIR $MYAPP_HOME
COPY --from=myapp-build $MYAPP_HOME/target/*.jar $MYAPP_HOME/myapp.jar

ENTRYPOINT java -jar myapp.jar
#running the jar
