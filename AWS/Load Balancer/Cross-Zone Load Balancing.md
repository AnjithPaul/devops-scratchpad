#aws #loadBalancer #networking 
## Cross-Zone Load Balancing
Considers all instance across all availability zone and **distrubute load evenly for all instances across all AZs**. Without Cross-zone load balancing, it will first divide load evenly between load balancers, then that will again be distrubuted between instances under each load balancer. so instances in zones with less instances will have higher load.
- [ ] ALB
	- [ ] can't be disabled
	- [ ] No charge for inter AZ data
- [ ] CLB
	- [ ] disabled by default
	- [ ] no charge for inter AZ data if enabled
- [ ] NLB
	- [ ] disabled by default
	- [ ] pay extra for inter AZ data if enabled