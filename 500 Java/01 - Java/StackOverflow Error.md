Backlink: [[Junit5]]

Exception in thread "main" java.lang.StackOverflowError
	at com.css.cloud.modules.approvalrules.ApprovalRulesApplication.factorial(ApprovalRulesApplication.java:36)


``` java
public static void main(String[] args) {  
  
   SpringApplication.run(ApprovalRulesApplication.class, args);  
   
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


StackOverflow happens when stack memory is not enough. 

