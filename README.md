# GeeksClub GitOps

## ArgoCD
https://argo-cd.readthedocs.io/en/stable/

```shell
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
kubectl apply -f argocd/application.yaml
# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
kubectl port-forward svc/argocd-server 8989:443 -n argocd
```