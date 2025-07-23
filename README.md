# quick-with-helm
helm quick sheet

#### Pre-requirement for helm are working
1. Kubectl 
2. Kubernetes cluster

#### Reference document link: https://helm.sh/docs/intro/install/

```
brew install helm
```

```
helm list

helm install <chart>
helm upgrade <chart>
helm delete <chart> or helm uninstall <chart>
```

#### Charts repository

ArtifactHub.io


```
helm search hub wordpress

helm search hub bitnami

helm repo add bitnami https://charts.bitnami.com/bitnami
helm install test-bitnami  bitnami/wordpress

helm list

helm uninstall test-bitnami
```


## Customize package deployment

```
helm install --set wordpressBlogname="Bitnami guide" --set wordpressEmail="test@gmail.com" test-bitnami  bitnami/wordpress

```

```
helm install --values custom-values.yaml test-bitnami  bitnami/wordpress
```

#### Package Life cycle


```
helm install nignx-test bitnami/nginx --version 7.1.0
kubectl get pods 
kubectl describe pod nginx-test-8038
```

```
helm upgrade nginx-test bitnami/nginx 
kubectl get pods 
kubectl describe pod nginx-test-905u

```


```
helm history nginx-test

