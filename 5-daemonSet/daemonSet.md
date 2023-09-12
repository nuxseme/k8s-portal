# daemonSet



### daemonSet.yaml

```yaml
apiVersion: apps/v1
kind: DaemonSet
metadata:
  creationTimestamp: null
  labels:
    app: nginx-ds
  name: nginx-ds
spec:
  selector:
    matchLabels:
      app: nginx-pod
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
      tolerations:
      - key: node-role.kubernetes.io/control-plane
        effect: NoSchedule
        operator: Exists
status: {}
```

