**Pre-requisite**

1)Docker installed

2)Minikube installed

3)Kubectl installed

**steps to install ArgoCD**
```
kubectl create ns argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.5.8/manifests/install.yaml
kubectl get all -n argocd
```
**Access ArgoCD UI on Browser**
```
kubectl port-forward svc/argocd-server -n argocd --address 0.0.0.0 8080:443
```
by doing this The ArgoCD UI will be available at http://localhost/IP:8080
