## Installing with HELM.
https://www.linuxtechi.com/how-to-install-kubernetes-dashboard/

## Install Helm
```bash
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
chmod 700 get_helm.sh
./get_helm.sh ```

## Add Kubernetes Dashboard Helm Repository
```bash
helm repo add kubernetes-dashboard https://kubernetes.github.io/dashboard/
helm repo list ```

##  Install Kubernetes Dashboard Using Helm
```bash
helm upgrade --install kubernetes-dashboard kubernetes-dashboard/kubernetes-dashboard --create-namespace --namespace kubernetes-dashboard ```

# Access dashboard from outside of Kubernetes cluster then expose the Kubernetes-dashboard deployment using NodePort type, as show below:
```bash
kubectl expose deployment kubernetes-dashboard --name k8s-svc --type NodePort --port 8443 -n kubernetes-dashboard ```

## Generate Token for Kubernetes Dashboard
kubectl create -f k8s-dashboard-account.yaml
serviceaccount/admin-user created
clusterrolebinding.rbac.authorization.k8s.io/admin-user created
