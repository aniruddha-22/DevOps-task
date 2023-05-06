# Use a base image with Maven installed
FROM maven:3.8.4-openjdk-8 AS builder

# Set the working directory in the container
WORKDIR /app

# Build the JAR file
RUN mvn clean install

# Create a new stage with a minimal runtime image
FROM openjdk:8-jre-slim

# Set the working directory in the container
WORKDIR /app

# Copy the compiled Java application into the container
COPY target/productcatalogue-0.0.1-SNAPSHOT.jar productcatalogue.jar

# Expose the desired port
EXPOSE 8020

# Specify the command to run when the container starts
CMD ["java","-Djava.security.egd=file:/dev/./urandom""-jar","pproductcatalogue.jar","server"]
