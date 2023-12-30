# Go-Lang Full Cycle deploy Kubernetes
Repositório para armazenar o código do módulo de deploy com kubernetes do curso Go Expert da Ful Cycle

## Acessando o container
```bash
docker compose exec goapp bash
```

## Gerando e rodando imagem Docker prod
```bash
docker build -t goapp:latest -f Dockerfile.prod .
docker run --rm -p 8080:8080 goapp:latest
```