5! = 120

``` java
public static void main(String[] args) {  
  
   SpringApplication.run(ApprovalRulesApplication.class, args);  
   System.out.println("test success");  
   System.out.println(LocalTime.now());  
  
   System.out.println(Integer.MAX_VALUE);  
   System.out.println(factorial(Integer.MAX_VALUE));  
   System.out.println(factorial(5));  
   System.out.println(factorial(3));  
}  
  

public static long factorial(long n){  
   if (n < 1) {  
      return 1;  
   }  
   else {  
      return n * factorial(n-1);  
   }  
}
```