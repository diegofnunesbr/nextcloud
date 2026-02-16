# nextcloud

Este guia descreve a instalação e remoção do **nextcloud** com o banco **mariadb** em um cluster Kubernetes, utilizando o manifesto `nextcloud.yaml`.

## Pré-requisitos

- `Kubernetes` instalado
- `kubectl` instalado
- `Ingress Controller NGINX` instalado
- `cert-manager` instalado
- `ClusterIssuer` instalado

## Estrutura do repositório

```text
nextcloud/
├── applications/
│   └── argocd.yaml     # Application do Argo CD
├── nextcloud.yaml      # Manifests do nextcloud
└── README.md
```

---

## Instalar o nextcloud

```bash
git clone https://github.com/diegofnunesbr/nextcloud.git
cd nextcloud
kubectl apply -f applications/argocd.yaml
```

## Acessar o nextcloud

https://nextcloud.diegofnunesbr.com/

## Remover o nextcloud

```bash
cd nextcloud
kubectl delete -f applications/argocd.yaml
kubectl delete namespace nextcloud --ignore-not-found
```
