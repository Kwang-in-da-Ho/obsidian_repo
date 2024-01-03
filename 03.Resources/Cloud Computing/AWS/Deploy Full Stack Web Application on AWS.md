## Prerequisites
### Backend Server code
* In `application.properties`, use environment variables to set DB Connection info
* Information about these env. variables can be found at 
	* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.managing.db.html
```properties
spring.datasource.url=jdbc:mysql://${RDS_HOSTNAME:localhost}:${RDS_PORT:3306}/${RDS_DB_NAME:social-media-database}  
spring.datasource.username=${RDS_USERNAME:social-media-user}  
spring.datasource.password=${RDS_PASSWORD:dummypassword}
```


## Steps
### Deploy backend
1. Create [[Elastic BeanStalk]] application and environment
2. When creating application, in **Application Code** section, choose *Upload your code*
3. Select your packaged `.jar` of your REST API server and upload
### Set RDB
1. Choose `Configure more options` at the bottom of Create new application page
2. Click Edit at the **Database** tab
3. 