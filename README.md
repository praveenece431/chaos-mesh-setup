# Chaos Mesh Installation

This guide outlines the steps to install Chaos Mesh using Helm on your Kubernetes cluster.

## Step 1: Add Chaos Mesh Helm Repository

Add the Chaos Mesh Helm repository to your Helm configuration.

```bash
helm repo add chaos-mesh https://charts.chaos-mesh.org
helm repo update
kubectl create ns chaos-testing

helm install chaos-mesh chaos-mesh/chaos-mesh \
  --namespace=chaos-testing \
  --set chaosDaemon.runtime=containerd \
  --set chaosDaemon.socketPath=/run/containerd/containerd.sock

