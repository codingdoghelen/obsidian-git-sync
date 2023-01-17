Backlink: [[Java]] [[Microservices]] [[00. Java JDK 17 Updates]]

``` java
var sorted = mongoTemplate.findAll(AutoDayEndDepartmentCode.class, COLLECTION_AUTO_DAY_END_DEPT_CODE)  
        .stream()  
        .sorted(Comparator.comparing(AutoDayEndDepartmentCode::id))  
        .collect(Collectors.toList());
```


``` java
Query query = new Query()

var first = mongoTemplate.findAllAndRemove(new Query(), COLLECTION_AUTO_DAY_END_DEPT_CODE);
```
