helm template . >> test.yaml ( to render helm chart)
kustomize build overlays/dev


helm install jenkins-kubernetes jenkins --create-namespace

helm install jenkins-kubernetes --namespace jenkins --create-namespace .

gcloud compute firewall-rules create http-node-port     --allow tcp:32000


konthamvivek13@gmail.com
vivekk
Ready2go@197