#This is multi-stage Dockerfile (build the artifact and copy the artifact into tomcat image)

# Stage 1: Build the artifact
FROM maven:3.9.9-eclipse-temurin-21-jammy AS BUILD_IMAGE
RUN git clone https://github.com/Padma-1/vprofile-project.git
RUN cd vprofile-project && git checkout local && mvn install

# Stage 2: Copy artifact into Tomcat image
FROM tomcat:10-jdk21
RUN rm -rf /usr/local/tomcat/webapps/* #removing the default application in a Tomcat image
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

# These commands are already set as the defaults in the official Tomcat base image, so explicitly repeating them is optional.
# But for modifying the port or to run other scripts, need to mention
EXPOSE 8080
CMD ["catalina.sh", "run"]
