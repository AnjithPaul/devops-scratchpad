#kubernetes #networking #ingress 
## TLS
- [ ] secure an Ingress by specifying a **Secret** that contains a TLS **private key and certificate**.
- [ ] assumes TLS termination at the ingress point
- [ ] If the TLS configuration section in an Ingress specifies **different** hosts, they are **multiplexed** on the same port according to the **hostname** specified through the **SNI** TLS extension
- [ ]  TLS will not work on the **default rule** because the certificates would have to be issued for all the possible **sub-domains**. Therefore, `hosts` in the `tls` section need to explicitly **match** the `host` in the `rules` section.

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: tls-example-ingress
spec:
  tls:
  - hosts:
      - https-example.foo.com
    secretName: testsecret-tls
  rules:
  - host: https-example.foo.com
    http:
      paths:
      - path: /
        pathType: Prefix
        backend:
          service:
            name: service1
            port:
              number: 80
```