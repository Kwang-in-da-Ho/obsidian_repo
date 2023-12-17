
* Building app on your local machine and copying it into a docker image is **Not Recommended**.
	* Output may be different depending on your environment
* Entire Build process should happen in the image build
## 1. Create `Dockerfile` in Your App
* The Dockerfile should be saved in your app's root directory*
* Dockerfile sample
```Dockerfile
FROM openjdk:18.0-slim    # base image on which you will build your image
COPY target/*.jar app.jar # copy files or directories into image
EXPOSE 5000               # port number that container listens to at runtime
ENTRYPOINT ["java", "-jar", "/app.jar"] # configure a command that will be run at container launch
```

## 2. Build Project
## 3. Run `docker build`
