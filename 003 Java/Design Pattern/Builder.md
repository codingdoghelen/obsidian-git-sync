Tag: [[Java]]

Builder is a [[Design Pattern]] that is commonly used for construction of ==step by step== method.

1. new Builder()
2. Use Constructor to set set set
3. At last .build

Builder as a director to do ordering.


``` java
public static class ComputerBuilder{  
	// required parameters  
    private String HDD;  
    private String RAM;  
    // optional parameters  
    private boolean isGraphicsCardEnabled;  
    private boolean isBluetoothEnabled;  
    
    public ComputerBuilder(String hdd, String ram){  
        this.HDD=hdd;  
        this.RAM=ram;  
    }  
    
    public ComputerBuilder setGraphicsCardEnabled(boolean isGraphicsCardEnabled) {  
        this.isGraphicsCardEnabled = isGraphicsCardEnabled;  
        return this;       
     }  
     
    public ComputerBuilder setBluetoothEnabled(boolean isBluetoothEnabled) {  
        this.isBluetoothEnabled = isBluetoothEnabled;  
	    return this;
        
    }  
    public Computer build(){  
	    return new Computer(this);  
    }  
}  
  
```



``` java
public class TestBuilderPattern {  
    public static void main(String[] args) {  
    //Using builder to get the object in a single line of code and   
    //without any inconsistent state or arguments management issues         
		Computer comp = new Computer.ComputerBuilder(  
                "500 GB", "2 GB").setBluetoothEnabled(true)  
                .setGraphicsCardEnabled(true).build();  
    }  
}
```


One of the most popular example will be [[Web Client]] which is made to call apis.

Builder is easily be seen in chained method i.e. 
``` Java
// In Main Class
@Bean
public WebClient.Builder getWebclientBuilder() {  
    return WebClient.builder();  
}

```

  Below Example also relates to [[String]] Library
  
``` Java
// In Controller Class
@GetMapping("/webclient-builder")  
public String globalGoldRateWebclient() {  
  
    String str = webClientBuilder.build()  
            .get()  
            .uri(url)  
            .retrieve()  
            .bodyToMono(String.class)  
            .block();  

    String parsed = StringUtils.substringAfter(str, "TWD=" + "\t");  
    String t = StringUtils.substringBefore(parsed, "\n");  
  
    return t;  
}
```


