# Kubernetes
Curso de Kubernetes da full cycle

## Comandos kind

- Criar novo cluster com kind
```sh
./kind create cluster
```

- Criando cluster a partir de um arquivo de config
```sh
~/./kind create cluster --config=k8s/kind.yaml --name=fullcycle
```

- Listando os clusters
```sh
./kind get clusters
```

- Excluindo um cluster
```sh
./kind delete clusters CLUSTER_NAME
```

## Comandos kubectl
- Logando no cluster criado com o kind no kubectl

```sh
kubectl cluster-info --context kind-kind
```

- Listando os nodes
```sh
kubectl get nodes
```

