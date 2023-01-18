Backlinks: [[00 Microservices]], [[01 Microservices Level 2 -  Fault Tolerance and Resilience]], [[Circuit Breaker Pattern]], [[Hystrix Dashboard]]

Tags: #Microservices 

# For Fault Tolerance - Hystrix

# What is Hystrix?

- Use to execute Circut Breaker Pattern
- Need to use proxy to control the service
- Provide fallbacks (Fallback mechanism)
- One Api calling two Apis, if one of them fails to perform, cut the circut -> granular fallback

![[hystrix.png]]

![[hystrix_config.png]]

# Hystrix Config
1st param: Timeout Time: 2000
2nd param: How many requests calling the api: 5
3rd param: Percentage of the requests i.e. 50% of 5 requests
4th param: How long the circut breaker has to sleep before it wakes up again: 5 seconds