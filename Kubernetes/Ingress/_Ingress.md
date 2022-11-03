#kubernetes #ingress #networking 
## Ingress
- [ ] An API object that **manages external access to the services** in a cluster, typically HTTP
- [ ] Ingress **exposes** **HTTP** and **HTTPS** **routes from outside** the cluster to services within the cluster.
- [ ] Traffic routing is controlled by **rules** defined on the **Ingress resource**
![ingress-diagram](https://d33wubrfki0l68.cloudfront.net/91ace4ec5dd0260386e71960638243cf902f8206/c3c52/docs/images/ingress.svg)
- [ ] An Ingress may be configured to give Services **externally-reachable URL**s, **load balance** traffic, terminate **SSL / TLS**, and offer **name-based virtual hosting.**

### Ingress Controller
- [ ] it **sets up an external load balancer** that connects to the **Ingress**, and then routes traffic to the service, following the set **rules**
- [ ] An **Ingress controller** is responsible for **fulfilling** the Ingress, usually with a **load balancer**. 
- [ ] Ingress resource without controller **has no effect**
- [ ] There are **different** variations of ingress controllers (e.g: AWS, nginx, etc)

### Ingress Resource
- [ ] The name of an Ingress object must be a valid **DNS subdomain name**
- [ ]  Ingress frequently uses **annotations** to configure some options depending on the Ingress controller
- [ ] it contains a list of **rules** matched against all incoming requests. each rule contain
	- [ ] optional **host**. if no host is specified, considers all inbound traffic
	- [ ] list of **paths**. each of which has an associated **backend** defined with a `service.name` and a `service.port.name` or `service.port.number`
- [ ] Request that do not match any rules are send to **defaultBackend** configured in **Ingress controller**
- [ ] If multiple paths match, precedence will be for **longest path**. If length are equal, precedence will be for **exact** pathType over prefix pathType
- [ ] pathTypes:
	- [ ] **ImplementationSpecific**:  matching is up to the IngressClass
	- [ ] **Exact**: Matches the URL path exactly
	- [ ] **Prefix**: Matches based on a URL path prefix split by `/` (`/foo/bar` matches`/foo/bar/baz`, but does not match `/foo/barbaz`)

### Ingress Class
- [ ] IngressClass resource contains **additional configuration** including the **name of the controller** that should implement the class
- [ ] Depreciated `kubernetes.io/ingress.class` reference the **name of the ingress controller**. ingressClassName  field is a reference to an IngressClass **resource** that contains **additional** Ingress configuration, **including** the name of the Ingress controller.

### Types of Ingress
1.  [[single Service]]
2. [[Simple fanout]]
3. [[Name based virtual hosting]]
4. [[TLS]]
5. [[Load Balancing]]

### Annotations
- [ ] Ingress frequently uses annotations to **configure** some options depending on the Ingress controller
- [ ] Annotations applied to **Service have higher priority** over annotations applied to Ingress
- [ ] Annotations that configures **LoadBalancer / Listener** behaviors have different **merge behavior** when **IngressGroup** feature is been used.
	- [ ] **Exclusive**: should only be specified on a **single Ingress** within IngressGroup **or** specified with **same value across** all Ingresses within IngressGroup
	- [ ] **Merge**: can be specified on all Ingresses within IngressGroup, and will be merged together.

### Ingress Group
- [ ] IngressGroup feature enables you to group **multiple Ingress** resources together.
- [ ] support them with a **single ALB**
- [ ] `alb.ingress.kubernetes.io/group.name` specifies the group name that this Ingress belongs to.
- [ ] `alb.ingress.kubernetes.io/group.order` specifies the **order** across all Ingresses **within** IngressGroup.


### Related
- [[Ingress vs Load Balancer]]
