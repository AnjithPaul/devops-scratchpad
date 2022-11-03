#aws #loadBalancer #security #networking #SSL #TLS
## SSL/TLS
- [[_SSL Certificate|SSL/TLS Certificate]] allow traffic to be **encrypted in transit** (in-flight encryption)
- [ ] SSL -> Secure Sockets Layer
- [ ] TLS -> Transport Layer Security (**Newer** version)
- [ ] Public SSL certificates are issued by **Certificate Authorities** (CA) .eg: GoDaddy
- [ ] SSL certificate has expiration date set by us (not CA)
- [ ] Users -> (HTTPS) -> LB -> (**HTTP**) -> EC2
- [ ] LB uses **X.509** certificate (SSL/TLS server Certificate)
- [ ] manage certificates using **AWS Certificate Manager**
	- [ ] Can upload our own certificate
- [ ] HTTPS Listener (LB Listener):
	- [ ] specify default certificate
	- [ ] can add optional list of certificates to support multiple domains
	- [ ] Clients can use **SNI** (Server Name Indication) to specify the hostname they reach
		- [ ] SNI sovles the problem of loading **multiple SSL certificates** (per listener rule) onto one web server (to serve multiple websites)
		- [ ] requires client to indicate the hostname of target server in initial SSL handshake. server will then find the **correct certificate** or return the default one
		- [ ] only **ALB, NLB & CloudFront**. CLB can have only one certificate
	- [ ] Ability to specify security policy to support older versions of SSL/TLS