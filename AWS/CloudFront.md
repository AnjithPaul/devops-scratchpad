#aws #networking #cloudFront
## CloudFront
- [ ] Content Delivery Network (**CDN**)
- [ ] Improves **read performance** by **caching** at ==edge location== (216 locations globally)
- [ ] **DDoS** protection, integration with **Shield** and **WAF**
- [ ] can expose **external HTTPS** and can talk to internal **HTTPS backends**
- [ ] Origins
	- [ ] **S3** bucket
		- [ ] Distrubute files and cache them at edge
		- [ ] Enhanced security with Cloudfront **Origin Access Identity** (OAI) which allow communication to s3 **ONLY** from cloudfront
		- [ ] can be used as an ingress to **upload** files to S3
	- [ ] Custom Origin (**HTTP**)
		- [ ] **ALB** or **EC2**
			- [ ] must add list of **IPs of all edge** locations in security group instead of OAI
		- [ ] S3 website (enable bucket as **static s3 website**)
		- [ ] Any **HTTP** backend
- [ ] **Geo Restriction**: uses 3rd party **Geo-IP database** to determine country 
- [ ] **Cache Invalidation**: force entire( * ) or partial (/path/* ) cache deletion so that updated content will be available in cache

### CloudFront vs S3 Cross Region Replication
##### CloudFront
- [ ] **Global** Edge network
- [ ] Files are **cached** for a **TTL**
- [ ] Great for **static** content that must be available **everywhere**

##### S3 Cross Region Replication
- [ ] Must be setup for **each region** 
- [ ] Files are update in **real-time**
- [ ] **Read only**
- [ ] Great for **dynamic** content that needs to be available at **low-latency** in **few region**