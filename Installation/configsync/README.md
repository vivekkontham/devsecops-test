

gsutil cp gs://config-management-release/released/latest/config-management-operator.yaml config-management-operator.yaml


kubectl create secret generic git-creds \
  --namespace=config-management-system \
  --from-literal=username=vivekkontham \
  --from-literal=token=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

  

kubectl create secret generic git-creds \
  --namespace=dso \
  --from-literal=username=vivekkontham \
  --from-literal=token=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


https://cloud.google.com/kubernetes-engine/enterprise/config-sync/docs/how-to/cluster-scoped-objects#configure_a_subset_of_clusters 


https://cloud.google.com/kubernetes-engine/enterprise/config-sync/docs/how-to/multiple-repositories


/home/riashivani9/devsecops-test/Installation/configsync/namespacerepo/namespaceconfig/applications/namespace/deployment/overlay-dso/kustomize build . --enable-helm


https://github.com/vivekkontham/namespacerepo 

https://github.com/vivekkontham/root-repo