# Kubernetes
Curso de Kubernetes da full cycle

## Ordem de importancia no kubernetes
1. Deployment
2. Replicaset
3. Pod

## Comandos kind

- Criar novo cluster com kind
```sh
~/./kind create cluster
```

- Criando cluster a partir de um arquivo de config
```sh
~/./kind create cluster --config=k8s/kind.yaml --name=fullcycle
```

- Listando os clusters
```sh
~/./kind get clusters
```

- Excluindo um cluster
```sh
~/./kind delete clusters fullcycle
```

## Comandos kubectl
- Logando no cluster criado com o kind no kubectl

```sh
kubectl cluster-info --context kind-fullcycle
```

- Listando os nodes
```sh
kubectl get nodes
```

- Listandos os clusters
```sh
kubectl config get-clusters
```

- Mudando para outro cluster (context)

```sh
kubectl config use-context kind-fullcycle
```

- Criando um pod
```sh
kubectl apply -f k8s/pods.yaml
```

- Excluindo um pod
```sh
kubectl delete pod POD_NAME
```

- Descrevendo/Analisando um pod
```sh
kubectl describe pod goserver-59d8849d76-7hj6b
```

- Compartilhando porta do pod temporariamente
```sh
kubectl port-forward pod/goserver 8080:8080
```

- Listando os replicasets
```sh
kubectl get replicasets
```

- Excluindo um replicaset
```sh
kubectl delete replicaset REPLICASET_NAME
```

- Rollout de deployments

```sh
kubectl rollout history deployment DEPLOYMENT_NAME
```

```sh
kubectl rollout undo deployment DEPLOYMENT_NAME
```

```sh
kubectl rollout undo deployment DEPLOYMENT_NAME --to-revision=1
```

- Redirecionando portas para o service
```sh
kubectl port-forward svc/goserver-service 8080:8080
```

- Utilizando o proxy para acessar a API do Kubernetes
```sh
kubectl proxy --port=8083
```
- Acessando a API
> http://127.0.0.1:8083/

- API de services
> http://127.0.0.1:8083/api/v1/namespaces/default/services/goserver-service