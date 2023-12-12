## 1. What is it?
* XML file that serves as the central configuration for a Maven project

## 2. Strucutre
```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"  
xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">  
<modelVersion>4.0.0</modelVersion>  
  
<!-- Basic project information -->  
<groupId>com.example</groupId>    <!-- id for project's group -->
<artifactId>my-app</artifactId>   <!-- id for project -->
<version>1.0-SNAPSHOT</version>   <!-- version of your project -->
<packaging>jar</packaging>  
  
<!-- Project dependencies -->  
<dependencies>  
<!-- Add your dependencies here -->  
</dependencies>  
  
<!-- Build configuration -->  
<build>  
<!-- Add build configuration here -->  
	<plugins>
		<!-- Plugins provide additional functionality during build process -->
	</plugins>
</build>  
</project>
```

## 3. Inheritence
* *