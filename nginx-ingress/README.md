helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm show values ingress-nginx/ingress-nginx > ingress-nginx-values.yaml
helm install [RELEASE_NAME] ingress-nginx/ingress-nginx
helm uninstall [RELEASE_NAME]

confiugration
https://github.com/kubernetes/ingress-nginx/tree/main/charts/ingress-nginx#configuration
