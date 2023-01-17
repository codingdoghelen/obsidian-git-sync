Tag: #unitTest

Dependency for [[Maven]]

``` pom
<properties>  
   <java.version>11</java.version>   // java version
   <maven.compiler.target>11</maven.compiler.target>  
   <maven.compiler.source>11</maven.compiler.source>
   <junit.jupiter.version>5.9.1</junit.jupiter.version>    
</properties>
```

``` pom
<dependency>  
   <groupId>org.junit.jupiter</groupId>  
   <artifactId>junit-jupiter-engine</artifactId>  
   <version>${junit.jupiter.version}</version>
   <scope>test</scope>  
</dependency>  

<dependency>  
   <groupId>org.junit.jupiter</groupId>  
   <artifactId>junit-jupiter-api</artifactId>
   <version>${junit.jupiter.version}</version>  
   <scope>test</scope>  
</dependency>

```


API:
Assert.Equals
AssertArrayEquals
AssertIterableEquals

Mark a message to notify what's the problem
![[assert_equals_message.png]]

![[assert_throw.png]]