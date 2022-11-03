#kubernetes #networking #ingress 
## Ingress backed by a single Service
- [ ] Expose a single service
- [ ] Can be done without ingress by using **LoadBalancer** or **NodePort** service types 
- [ ] With Ingress this can be done by specifying a **default backend** with no rules

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: test-ingress
spec:
  defaultBackend:
    service:
      name: test
      port:
        number: 80
```