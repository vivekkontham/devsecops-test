Install Helm,git and Kubectl
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
sudo apt-get install apt-transport-https --yes
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
sudo apt-get install kubectl
sudo apt-get install git



Install DefectDojo 

helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update

git clone https://github.com/DefectDojo/django-DefectDojo
cd django-DefectDojo

helm dependency update ./helm/defectdojo

DJANGO_INGRESS_ENABLED=false
DJANGO_INGRESS_ACTIVATE_TLS=false

helm install   defectdojo   ./helm/defectdojo   --set django.ingress.enabled=${DJANGO_INGRESS_ENABLED}   --set django.ingress.activateTLS=${DJANGO_INGRESS_ACTIVATE_TLS}   --set createSecret=true   --set createRedisSecret=true   --set createPostgresqlSecret=true

k9s

Update config map defectdojo and DD_ALLOWED_HOSTS value  TO "*"

Update the kubernete service type to LoadBalancer


To find out the password, run the following command:

    echo "DefectDojo admin password: $(kubectl \
      get secret defectdojo \
      --namespace=default \
      --output jsonpath='{.data.DD_ADMIN_PASSWORD}' \
      | base64 --decode)"

URL: http://34.47.236.176/dashboard
UserName : vivekk
Password: Ready2go@197


https://github.com/DefectDojo/django-DefectDojo/blob/master/readme-docs/KUBERNETES.md 