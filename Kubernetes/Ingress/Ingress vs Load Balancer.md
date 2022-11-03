#kubernetes #networking #ingress #loadBalancer 
## Ingress vs Kubernetes Load Balancer
- [ ] a `type=LoadBalancer` on a service, kubernetes will ==provision a separate ELB for each service==, Meaning if you have 5 services with `type=LoadBalancer`, you get **5 ELB**s. By using **ingress controller** it will create a **single ELB**
- [ ] Internet -> Ingress -> K8s Services -> Replicas
- [ ] load balancers are external to the cluster and only route to a **single service**
	- [ ] ingresses are native objects (**not service**) inside the cluster that can route to **multiple services**
- [ ] A kubernetes LoadBalancer service is a **service** that points to external load balancers that are NOT in your kubernetes cluster.
	- [ ] An ingress is really just a **set of rules** to pass to a controller that is listening for them.
- [ ] The big downside is that **each service** you expose with a LoadBalancer will get its own IP address
	- [ ] Ingress is the most useful if you want to expose multiple services under the same IP address
- [ ] Lets say you have 10 websites hosted in your cluster and you want to expose them all to external traffic.
	- [ ] If you use type LoadBalancer Service you'll spawn **10** HA Cloud load balancers (each costs money)
	- [ ] If you use type Ingress Controller you'll spawn **1** HA Cloud load balancer(saves money), and it'll point to an Ingress **Controller** running in your cluster.
- [ ]  load balancer distributes the requests among multiple backend services (of same type)
	- [ ] ingress is more like an API gateway (reverse proxy) which routes the request to a specific backend service based on, for instance, the URL.
