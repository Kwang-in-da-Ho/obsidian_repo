## 1. Characteristics
* Cross-Platform Tool
	* Maven - Java specific
* Completely Programmable
	* flexibility
	* DSL(Domain Specific Language) - Groovy / Kotlin
* Faster Build
	* **Incrementality** - runs only what is neccessary
		* compile only changed files
	* Build Cache - Reuses the build outputs of other Gradle builds with the same inputs
## 2. Core Files
### build.gradle
```groovy
plugins {
	id 'org.springframework.boot' version '3.1.1'
	id 'io.spring.dependency-management' version '1.1.0'
	id 'java'
}

group = 'com.in28minutes'
version = '0.0.1-SNAPSHOT'
sourceCompatibility = '17'

repositories {
	mavenCentral()
	maven { url 'https://repo.spring.io/milestone' } //additional repos
}

dependencies {
	implementation 'org.springframework.boot:spring-boot-starter-web'
	implementation 'org.springframework:spring-core'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
}

tasks.named('test') {
	useJUnitPlatform()
}

tasks.register('helloWorld'){
	doLast {
		System.out.println("Hello World");
	}
}
```
### settings.gradle
```groovy
pluginManagement {
	repositories {
		maven { url 'https://repo.spring.io/milestone' }
		gradlePluginPortal()
	}
}
rootProject.name = 'learn-gradle' //project name
```