


# deploiement en prod

helm upgrade --install myapp HELM/ --values HELM/values.yaml -n helm --create-namespace

<!-- helm upgrade --install myapp-release-prod myapp1/ --values myapp1/values.yaml  -n helm --create-namespace -->

kubectl apply -f HELM/clusterissuer-prod.yaml


--------------


helm upgrade --install app HELM --values=values.yml --namespace helm


---- command used
helm install my-app --namespace helm ./HELM


helm uninstall my-app -n helm