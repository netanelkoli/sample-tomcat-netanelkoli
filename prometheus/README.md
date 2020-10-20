This README file instruct how to deploy:

Prometheus-operator on EKS cluster

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update

helm upgrade --install prometheus prometheus-community/kube-prometheus-stack -f values.yaml -n monitoring --create-namespace

The prometheus will be avaiable on :
  $ echo $(kubectl get svc -n monitoring prometheus-kube-prometheus-prometheus -o jsonpath='{.status.loadBalancer.ingress[].ip}'):9090
