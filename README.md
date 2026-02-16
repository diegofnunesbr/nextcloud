# Nextcloud

Este guia descreve a instalação e remoção do **Nextcloud** com o banco **MariaDB** em um cluster Kubernetes, utilizando o manifesto `nextcloud.yaml`.

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
│   └── argocd.yaml        # Application do Argo CD
├── nextcloud.yaml         # Manifests do Nextcloud
└── README.md
```

---

## Instalar o Nextcloud

```bash
git clone https://github.com/diegofnunesbr/nextcloud.git
cd nextcloud
kubectl apply -f applications/argocd-nextcloud.yaml
```

## Acessar o Nextcloud

https://nextcloud.diegofnunesbr.com/

## Remover o Nextcloud

```bash
cd nextcloud
kubectl delete -f applications/argocd-nextcloud.yaml
kubectl delete namespace nextcloud --ignore-not-found
```
