Each time Junit runs a test, it starts a new instance. So it is anti-pattern to share variables from method A to method B. Instead, shd create a @BeforeEach init method to let junit starts it every time it calls a test method.

```junit
@BeforeEach  
void init() {  
    log.info("startup");  
  
    GenerateReportPathResponse response = new GenerateReportPathResponse();  
    response.setUrl(url);  
    response.setReport(report);  
  
    map.put("PSR136", response);  
}
```

![[before_all.png]]

**Important**
Junit @BeforeAll and @AfterAll are initialized before the class MathUntilsTest is initialized. This is why if they are needed, we need to use static methods, since static methods dont care when the class is initialized.

Other Annotations: 
@Disabled / @DisplayName / @Nested / @Repeated / 
@Tag - Use for differentiating unit tests and integration tests
 

![[nested.png]]
assumeTrue
![[assue_true.png]]

![[testInfo_and_testReporter.png]]