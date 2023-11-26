# Chaos Mesh Installation
https://mattermost.com/blog/how-to-break-stuff-chaos-engineering-and-chaos-mesh/#installing

https://chaos-mesh.org/docs/production-installation-using-helm/

https://chaos-mesh.org/docs/simulate-network-chaos-on-kubernetes/

https://github.com/chaos-mesh/chaos-mesh/tree/master/examples

This guide outlines the steps to install Chaos Mesh using Helm on your Kubernetes cluster.

## Add Chaos Mesh Helm Repository

Add the Chaos Mesh Helm repository to your Helm configuration.

```bash
helm repo add chaos-mesh https://charts.chaos-mesh.org
helm repo update
kubectl create ns chaos-testing
helm install chaos-mesh chaos-mesh/chaos-mesh \
  --namespace=chaos-testing \
  --set chaosDaemon.runtime=containerd \
  --set chaosDaemon.socketPath=/run/containerd/containerd.sock

