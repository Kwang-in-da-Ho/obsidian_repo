
* Building app on your local machine and copying it into a docker image is **Not Recommended**.
	* Output may be different depending on your environment
* Entire Build process should happen in the image build
* In multistage build, for base images in FROM clause, use separate images for each stage that serve different purposes

### Docker Layer
* each stage has layer*

## 1. Create `Dockerfile` in Your App
* The Dockerfile should be saved in your app's root directory*
* Dockerfile sample
* 
```Dockerfile
# Stage 1. All 
FROM maven:3.8.6-openjdk-18-slim AS build
WORKDIR /home/app

COPY ./pom.xml /home/app/pom.xml
COPY ./src/main/java/com/in28minutes/rest/webservices/restfulwebservices/RestfulWebServicesApplication.java	/home/app/src/main/java/com/in28minutes/rest/webservices/restfulwebservices/RestfulWebServicesApplication.java

RUN mvn -f /home/app/pom.xml clean package

COPY . /home/app
RUN mvn -f /home/app/pom.xml clean package

FROM openjdk:18.0-slim
EXPOSE 5000
COPY --from=build /home/app/target/*.jar app.jar
ENTRYPOINT [ "sh", "-c", "java -jar /app.jar" ]container launch
```

## 2. Build Project
## 3. Run `docker build`
