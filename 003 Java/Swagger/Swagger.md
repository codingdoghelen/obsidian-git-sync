## io.springfox >= 2.X


```xml
<dependency>
  <groupId>io.springfox</groupId>
  <artifactId>springfox-swagger-ui</artifactId>
  <version>2.9.2</version>
</dependency>
<dependency>
  <groupId>io.springfox</groupId>
  <artifactId>springfox-swagger2</artifactId>
  <version>2.9.2</version>
</dependency>
<dependency>
  <groupId>io.springfox</groupId>
  <artifactId>springfox-schema</artifactId>
  <version>2.9.2</version>
</dependency>
```


```
 http://localhost:8080/swagger-ui.html
```



## io.springfox >= 3.X
```xml
<dependency>
 <groupId>io.springfox</groupId>
 <artifactId>springfox-boot-starter</artifactId>
 <version>3.0.0</version>
</dependency>
```

browser URL
**Must need the swagger-ui==/==**

```
http://localhost:8080/swagger-ui/
http://localhost:8080/swagger-ui/index.html
```

![[api-doc.png]]

Annotation
``` java
@Configuration
@EnableSwagger2
```


![[swagger-ui.png | 1=200]]
![[java_code_to_swagger.png]]