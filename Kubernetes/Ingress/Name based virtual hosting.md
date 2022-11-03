#kubernetes #networking #ingress 
## Name based virtual hosting
- [ ] routing HTTP traffic to **multiple host** names at the same IP address
![ingress-namebase-diagram](https://d33wubrfki0l68.cloudfront.net/638e6be4c880b8497c7abd899c2bb0f972389c04/55a48/docs/images/ingressnamebased.svg)

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: name-virtual-host-ingress
spec:
  rules:
  - host: foo.bar.com
    http:
      paths:
      - pathType: Prefix
        path: "/"
        backend:
          service:
            name: service1
            port:
              number: 80
  - host: bar.foo.com
    http:
      paths:
      - pathType: Prefix
        path: "/"
        backend:
          service:
            name: service2
            port:
              number: 80
```