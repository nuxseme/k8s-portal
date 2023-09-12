# cronJob

```yaml
apiVersion: batch/v1
kind: CronJob
metadata:
  name: hello
spec:
  schedule: "* * * * *"
  jobTemplate:
    spec:
      template:
        spec:
          containers:
          - name: hello
            image: busybox:1.28
            imagePullPolicy: IfNotPresent
            command:
            - /bin/sh
            - -c
            - date; echo Hello Kubernetes Cluster\n; env
            env:
              - name: MY_NODE_NAME
                valueFrom:
                  fieldRef:
                    fieldPath: spec.nodeName
              - name: MY_POD_NAME
                valueFrom:
                  fieldRef:
                    fieldPath: metadata.name
              - name: MY_POD_NAMESPACE
                valueFrom:
                  fieldRef:
                    fieldPath: metadata.namespace
              - name: MY_POD_IP
                valueFrom:
                  fieldRef:
                    fieldPath: status.podIP
          restartPolicy: OnFailure
```

