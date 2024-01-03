## Prerequisites
### Backend Server code
#### DB Connection
* In `application.properties`, use environment variables to set DB Connection info
* Information about these env. variables can be found at 
	* https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/using-features.managing.db.html
```properties
spring.datasource.url=jdbc:mysql://${RDS_HOSTNAME:localhost}:${RDS_PORT:3306}/${RDS_DB_NAME:social-media-database}  
spring.datasource.username=${RDS_USERNAME:social-media-user}  
spring.datasource.password=${RDS_PASSWORD:dummypassword}
```
#### Security Policy
* All API calls to the root URL `/` must be permitted
	* ELB runs health check on application deploy, and this health check is done by sending request to root URL
```java
@Configuration  
public class SpringSecurityConfiguration {  
      
    @Bean  
    public SecurityFilterChain filterChain(HttpSecurity http) throws Exception {  
         
//     1) All requests should be authenticated  
       http.authorizeHttpRequests(  
             auth -> auth  
                .requestMatchers("/").permitAll() //#CHANGE  
                .anyRequest().authenticated()  
             );  
//     2) If a request is not authenticated, a web page is shown  
       http.httpBasic(withDefaults());  
         
//     3) CSRF -> POST, PUT  
       http.csrf(csrf -> csrf.disable());  
       
       return http.build();  
    }  
  
}
```
* Make sure the correct CORS policy is set for Front-end app API call*
## Steps
### Deploy backend
1. Create [[Elastic BeanStalk]] application and environment
2. When creating application, in **Application Code** section, choose *Upload your code*
3. Select your packaged `.jar` of your REST API server and upload
### Set RDB
1. Choose `Configure more options` at the bottom of Create new application page
2. Click Edit at the **Database** tab
3. Choose the desired database type and type in basic credential info