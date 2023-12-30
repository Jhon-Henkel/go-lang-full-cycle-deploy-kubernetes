# Go-Lang Full Cycle deploy Kubernetes
Repositório para armazenar o código do módulo de deploy com kubernetes do curso Go Expert da Ful Cycle

## Dependências
- [Kind](https://kind.sigs.k8s.io/docs/user/quick-start/)
- [Kubernetes](https://kubernetes.io/docs/tasks/tools/)

## Acessando o container
```bash
docker compose exec goapp bash
```

## Gerando e rodando imagem Docker prod
```bash
docker build -t jhowrf/goapp:latest -f Dockerfile.prod .
docker run --rm -p 8080:8080 jhowrf/goapp:latest
```

## Deploy no Kubernetes
```bash
kind create cluster --name=goexpert
kubectl apply -f k8s/deployment.yaml
kubectl apply -f k8s/service.yaml
kubectl port-forward svc/serversvc 8080:8080 # Para rodar localmente
```