#aws #loadBalancer #stickySession #CLB #ALB #networking 
## Sticky Sessions
- [ ] same client -> same instance
- [ ] CLB & ALB
- [ ] Cookie
	- [ ] Application-based Cookie
		- [ ] Custom cookie
			- [ ] generated by target (**application**)
			- [ ] can include **custom attributes** required by application
			- [ ] cookie name must be specified individually for each target group
		- [ ] Application cookie
			- [ ] generated by LB
			- [ ] cookie name is **AWSALBAPP**
	- [ ] Duration-based cookie
		- [ ] generated by LB
		- [ ] cookie name is **AWSALB** for ALB, and **AWSELB** for CLB
- [ ] Pros
	- [ ] Makes sure user doesn't lose session data
- [ ] Cons
	- [ ] could bring imbalance to load over backend instances