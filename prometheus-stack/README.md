helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update

https://github.com/prometheus-community/helm-charts/tree/main/charts/kube-prometheus-stack


grafana initial password
admin:prom-operator

# How to get ID/Password
kubectl get secret prometheus-stack-grafana -o jsonpath="{.data.admin-user}" | base64 --decode ; echo
kubectl get secret prometheus-stack-grafana -o jsonpath="{.data.admin-password}" | base64 --decode ; echo

# Link
Grafana nginx ingress setup: https://forcloud.tistory.com/206

# Issues
- Grafana ingress setup
  - While subdomain is working as expected, it is inpossible to use 'path' becuase it depends on grafana.ini
  - if 'path' is used for grafana ingress such as domain.com/grafana, it is always redirected to domain.com/login when trying to connect domain.com/grafana. Becausae of that, it returns 404 error
  - To avoid this isseu,
