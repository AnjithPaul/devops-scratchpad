#aws #loadBalancer #ec2
## Deregistration Delay
- [ ] Connection Draining - for CLB
- [ ] Deregistration Delay - for **ALB & NLB**
- [ ] Time to complete "**in-flight requests**" while instance is de-registering or unhealthy
- [ ] **Stops sending new request** to EC2 instance which is de-registering
- [ ] 1-3600 sec. Default 300 sec. 0 means disabled.
- [ ] EC2 instance will be **decommissioned only after** Deregistration Delay