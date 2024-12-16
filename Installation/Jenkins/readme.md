helm template . >> test.yaml ( to render helm chart)
kustomize build overlays/dev


helm install jenkins-kubernetes jenkins --create-namespace