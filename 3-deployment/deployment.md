# Deployment

### Deploy.yaml

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  creationTimestamp: null
  labels:
    app: nginx-deploy
  name: nginx-deploy
spec:
  replicas: 3
  selector:
    matchLabels:
      app: nginx-pod
  strategy: {}
  template:
    metadata:
      creationTimestamp: null
      labels:
        app: nginx-pod
    spec:
      volumes:
      - name: nginx-config
        configMap:
          name: nginx-config
      containers:
      - image: nginx:alpine
        name: nginx
        resources: {}
        volumeMounts:
        - mountPath: /etc/nginx/conf.d
          name: nginx-config
status: {}
```

