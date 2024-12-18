helm repo add argo https://argoproj.github.io/argo-helm
helm template argo argo/argo-cd --output-dir argocd-manifests

helm show values argo/argo-cd > values.yaml

helm show values argo/argo-cd > values.yaml

kubectl create namespace argocd
helm install --values values.yaml argocd argo/argo-cd --namespace argocd

kubectl get nodes -o wide
kubectl get pods -n argocd -o wide
kubectl get svc -n argocd -o wide

Update svc  argocd-server to LoadBalancer or NodePort
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode ; echo


https://devopscube.com/setup-argo-cd-using-helm/