#aws #loadBalancer #NLB #networking 
## Network Load Balancer
- [ ] TCP, TLS (Secure TCP), UDP
- [ ] Layer **4 only**
- [ ] **High performance**
	- [ ] handle millions of request per seconds
	- [ ] less latency (100ms) (vs 400ms for ALB)
- [ ] **One Fixed static IP per AZ**
- [ ] supports assigning **elastic IP** (helpful when need to specify which IP can access application)
- [ ] Target group
	- [ ] **EC2**
	- [ ] Private **IP**s
	- [ ] **ALB**
		- [ ] NLB + ALB -> e.g: NLB for fixed IP and ALB for path based routing
- [ ] Health check support **TCP, HTTP, and HTTPS**
- [ ] Security group of target group should allow **HTTP from 0.0.0.0/0** as it'll look like traffic is coming from outside instead of NLB's IP