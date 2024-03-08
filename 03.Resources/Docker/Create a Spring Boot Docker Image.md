
* Building app on your local machine and copying it into a docker image is **Not Recommended**.
	* Output may be different depending on your environment
* Entire Build process should happen in the image build
* In multistage build, for base images in `FROM` clause, use separate images for each stage that serve different purposes

### Docker Build Layer
* Docker caches every layer (command in Dockerfile) and tries to reuse it
* Use this feature to reduce your build time!


## 1. Create `Dockerfile` in Your App
* The Dockerfile should be saved in your app's root directory*
* Dockerfile sample
* 
```Dockerfile
# Stage 1. All the important things that do not change and are reused througut build process
# 1-1. set base image
FROM maven:3.8.6-openjdk-18-slim AS build
# 1-2. All subsequent commands should be run under this directory
WORKDIR /home/app

# Stage 2. Copy the files that do not change often and takes long time to build (dependency-related codes)
COPY ./pom.xml /home/app/pom.xml
COPY ./src/main/java/com/sample/demodocker/DeomDockerApplication.java /home/app/src/main/java/com/sample/demodocker/DeomDockerApplication.java 

# Stage 3. Run build out of the codes that do not change often
RUN mvn -f /home/app/pom.xml clean package

# If there were no changes in the above 5 layers, they will be reused
# By doing this, you will need much less time to build later

# Stage 4. Copy the files that change often and build
COPY . /home/app
RUN mvn -f /home/app/pom.xml clean package

FROM openjdk:18.0-slim
EXPOSE 5000
COPY --from=build /home/app/target/*.jar app.jar
ENTRYPOINT [ "sh", "-c", "java -jar /app.jar" ]container launch
```

## 2. Run `docker build`

## Spring Boot  Maven Plugin
* Provides Spring Boot support in Apache Maven
### Commands
* `mvn spring-boot:repackage`
* `mvn spring-boot:run`
* `mvn spring-boot:start`*
* `mvn spring-boot:build-image` : Build a Docker Image
	* provides very efficient image build
	* requires **Java 17+** versions to use