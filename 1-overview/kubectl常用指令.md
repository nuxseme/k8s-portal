# Kubectl 常用指令



- kubectl api-resources #获取所有kubectl apiserver 指令及简写

- kubectl  get  node #获取所有可用节点

- kubectl get  deployment #获取所有部署

- kubectl  get all

- kubectl get pod $podName -o wide #查看ip

- kubectl describe  $object $objectName

- kubectl logs pod  $podName

- kubectl  get  event

- kubectl port-forward $serviceName $localPort:$servicePortName|$servicePort

- kubectl describe cm #查看配置




### kubeadm

- sudo kubeadm init --pod-network-cidr=10.10.0.0/16  --apiserver-advertise-address=$hostIp
- systemctl stop firewalld.service
- kubeadm reset
- iptables -F && iptables -t nat -F && iptables -t mangle -F && iptables -X

