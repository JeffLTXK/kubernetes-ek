# Demo Kubernetes Project
## Kind Cluster Setup
1.  Deploy Kind to your environment.
2.  Deploy cluster using command:
`kind create cluster --config=./cluster/kind-cluster-config.yaml`

## Kubernetes Namespace
1.  Run the following command to deploy your kubernetes namespace 'kube-logging'
`kubectl create -f ./cluster/kube-logging-namespace.yaml`

## Elasticsearch
1.  Create the elasticsearch service:
`kubectl create -f ./elasticsearch/elasticsearch-service.yaml`
2.  Create the elasticsearch stateful set:
`kubectl create -f ./elasticsearch/elasticsearch-statefulset.yaml`

## Kibana
1.  Create the kibana stateful set:
`kubectl create -f ./kibana/kibana-statefulset.yaml`

## NGINX
1.  Create the NGINX configmap
`kubectl create configmap confnginx -n kube-logging --from-file=./nginx/.data/nginx.conf`
2.  Create the NGINX service 
`kubectl create -f ./nginx/nginx-service.yaml`
3.  Create the NGINX deployment
`kubectl create -f ./nginx/nginx-deploy.yaml'
