Backlinks: [[00 Microservices]], [[Timeouts]], [[Java]], [[Hystrix]]
Tags: #Microservices

Multi-threading Issues:

![[threads_problem.png]]
Number of concurrent thread didnt reach the limit, if more requests for B, it will be stuck at the thread and cannot free up. So even A is fast, ppl still find it slow as threads for B are still working.

---

How to solve the problem: **Using Timeouts**

Yet Timeout cannot solve all the problems. [Youtube - haven't solved it yet](https://youtu.be/uskKJoCd7ww)
```
Eg Set Timeout for 3000ms
But request comes in 1000ms
The amount of requests is higher than the amt of timeout
The threads still stuck in web server
```

![[still_cannot_solve_the_problem.png]]

---

## The Only Solution: [[Circuit Breaker Pattern]]
[Youtube - Circuit breaker pattern explain](https://youtu.be/mJ8JSach2P4)
Assume that Movie Info Service has too many requests and [[Timeouts]] cannot help.
Movie Catalog Service will auto detect if Movie Info Service is having too many requests. If it does, it will stop the service and block requests towards Movie Info. Requests still can be called for Rating Data Service. Later on if Movie Info Service is detected it is fine, it will unblock the Movie Info and everything works again. 

![[circuit_breaker_pattern.png]]

---

# Fallback Mechanism

![[fallback_recommedation.png]]

Thow error: Not Recommeded uncless it is absoltely required.

Recommended: 
- Return a fallback "default" response
- Save previous responses (cache) and use that when possible - Bonus: Consumers dont even know it is down

---
# Why circut breakers?
1. Fail Fast
2. Fallback functionality
3. Automatic recovery
---
# Hystrix [[Hystrix]]
