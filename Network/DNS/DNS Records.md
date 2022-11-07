#networking #DNS #route53 

contains:
- [ ] Domain/subdomain Name 
- [ ] Record **Types**
	- [ ]  **A** - hostname to IPv4
	- [ ] **AAAA** - hostname to IPv6
	- [ ] **CNAME** - hostname to hostname
		- [ ] target is domain name which must have A or AAAA record
		- [ ] can't create CNAME record for top node of a DNS namespace (Zone Apex)
			- [ ] can't create for example.com but can create for www. example.com
	- [ ] **NS** - Name servers for the [[Hosted Zones]]
		- [ ] control how traffic is routed for a domain
		- [ ] respond to the DNS queries for the hosted zone
- [ ] Value
	- [ ] IP address
- [ ] Routing Policy
	- [ ] how AWS route 53 respond to queries
- [ ] TTL