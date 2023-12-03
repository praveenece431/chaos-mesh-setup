## Installation of metrics server:
# https://www.linuxtechi.com/how-to-install-kubernetes-metrics-server/
curl -LO https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml

# Edit the components.yaml with below:
vim components.yaml
Find the args section under the container section, add the following line:
- --kubelet-insecure-tls

Under the spec section, add following parameter,
hostNetwork: true

# Deploy metrics server:
kubectl apply -f components.yaml

# Verify Metrics Server Deployment
kubectl get pods -n kube-system
