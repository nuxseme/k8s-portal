# Ingress

<img src="../images/6bd934a9c8c81a9f194d2d90ede172af.png" alt="img" style="zoom:25%;" />

<img src="../images/bb7a911e10c103fb839e01438e184914.png" alt="img" style="zoom:25%;" />



### ingress

```yaml
apiVersion: networking.k8s.io/v1
kind: IngressClass
metadata:
  name: nginx-ingressclass

spec:
  controller: nginx.org/ingress-controller

---

apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  creationTimestamp: null
  name: nginx-ingress
spec:
  ingressClassName: nginx-ingressclass
  rules:
  - host: nginx-test.com
    http:
      paths:
      - backend:
          service:
            name: nginx-service
            port:
              number: 80
        path: /
        pathType: Exact
status:
  loadBalancer: {}
```

