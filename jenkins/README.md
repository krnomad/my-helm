helm repo add jenkins https://charts.jenkins.io
helm show values jenkins/jenkins > jenkins-values.yaml
helm install jenkins jenkins/jenkins -f jenkins-values.yaml
