**Pre-requisite**

1)Docker installed

2)Minikube installed

3)Kubectl installed

![Main](https://github.com/user-attachments/assets/a55cfe64-a93f-47bd-99ec-69fe94228767)

**steps to install ArgoCD**
```
kubectl create ns argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/v2.5.8/manifests/install.yaml
kubectl get all -n argocd
```
**Access ArgoCD UI on Browser**

By doing this The ArgoCD UI will be available at http://localhost/IP:8080
```
kubectl port-forward svc/argocd-server -n argocd --address 0.0.0.0 8080:443
```
Get the initial password for the admin user to log in
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```
reflink : https://blog.kubekode.org/setup-minikube-on-aws-ec2-instance
          
https://www.fosstechnix.com/how-to-install-argocd-on-minikube/

**To access the application**
```
 kubectl port-forward --address 0.0.0.0 svc/petclinic 9000:80
```
By doing this the application will be available at http://localhost/IP:9000
