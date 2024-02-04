# Find repo and
helm repo list
- output example
    ```
    NAME                	URL
    jenkins             	https://charts.jenkins.io
    bitnami             	https://charts.bitnami.com/bitnami
    brigade             	https://brigadecore.github.io/charts
    ingress-nginx       	https://kubernetes.github.io/ingress-nginx
    prometheus-community	https://prometheus-community.github.io/helm-charts

    ```

# Search repo with repo_name
helm search repo [repo name]
helm search repo ingress-nginx
- example
    ```
    NAME                       	CHART VERSION	APP VERSION	DESCRIPTION
    ingress-nginx/ingress-nginx	4.9.1        	1.9.6      	Ingress controller for Kubernetes using NGINX a...
    ```

# Install chart - release creation
helm install [release_name] [repo_name] [option]
helm install ingress-nginx ingress-nginx/ingress-nginx -f nginx-ingress/ingress-nginx-values.yaml


# Upgrade charts
helm upgrade [releaes name] [charts] [flags]
helm upgrade prometheus-stack prometheus-community/kube-prometheus-stack -f prometheus-stack-values.yaml
- If charts exist in the current folder
  helm upgrdae prometheus-stack .

# Chart development
- Pull chart with pull command (tar.gz downlaoded)
  helm pull jenkins/jenkins
  helm fetch prometheus-community/prometheus-stack --untar
- tar zxvf
- change chart



# Link
- https://forcloud.tistory.com/206

# Issue
- Grafana redirection if path is used for ingress
  solution: https://move02.github.io/articles/2021-10/Kubernetes-%EB%AA%A8%EB%8B%88%ED%84%B0%EB%A7%81-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EA%B5%AC%EC%B6%95

