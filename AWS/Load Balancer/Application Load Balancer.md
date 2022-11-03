#aws #loadBalancer #ALB #networking 
## Application Load Balancer
- [ ] HTTP, HTTPS, WebSocket
- [ ] Layer **7 only**
- [ ] load balance to multiple HTTP applications **across machines** (**Target groups**)
	- [ ] Health Check done at target group level
	- [ ] Types of target group
		- [ ] **EC2** instances (managed by ASG) - HTTP
		- [ ] **ECS tasks**  - HTTP
		- [ ] **Lambda** functions - HTTP request translated to JSON event
		- [ ] Private **IP**s
		- [ ] **ALB**
- [ ] load balance to multiple applications on same machine (e.g: containers)
- [ ] Support redirects (eg.:HTTP to HTTPS )
- [ ] Routing table to different target group (Rules)
	- [ ] based on 
		- [ ] path in URL (example.com **/test** )
		- [ ] hostname in URL (**test1.** example.com)
		- [ ] Query string (example.com/test? **id=1**)
		- [ ] HTTP Header
		- [ ] HTTP request method
		- [ ] Source IP
	- [ ] Because of this, **one ALB can handle request to multiple api endpoints/microservices** . where as it would have required one CLB per path.
- [ ] FIxed hostname 
- [ ] Application server don't see the IP of client directly. it will be inserted in the header **X-Forwarded-For**. and port in **X-Forwarded-Port** and protocol in **X-Forwarded-Proto**.

