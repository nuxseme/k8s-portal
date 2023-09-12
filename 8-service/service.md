# service

<img src="../images/0347a0b3bae55fb9ef6c07469e964b74.png?" alt="img" style="zoom:20%;" />

<img src="../images/fyyebea67e4471aa53cb3a0e8ebe624a.png" alt="img" style="zoom:25%;" />





### Service.yaml

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: null
  labels:
    app: service
  name: nginx-service
spec:
  ports:
  - port: 80
    protocol: TCP
    targetPort: 80
  selector:
    app: nginx-pod
  type: NodePort
```

