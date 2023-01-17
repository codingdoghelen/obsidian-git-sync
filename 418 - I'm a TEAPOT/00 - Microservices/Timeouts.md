Backlinks: [[Microservices]], [[Java]]

Setting [[RestTemplate]] Timeout

``` java
@LoadBalanced  
@Bean  
public RestTemplate getLoadBalancedRestTemplate(){  
    HttpComponentsClientHttpRequestFactory clientHttpRequestFactory = new HttpComponentsClientHttpRequestFactory();  
    clientHttpRequestFactory.setConnectTimeout(3000);  
    return new RestTemplate(clientHttpRequestFactory);  
}
```

