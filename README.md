# Nextcloud

Este guia descreve a instalação e remoção do **Nextcloud** com o banco **MariaDB** em um cluster Kubernetes, utilizando o manifesto `nextcloud.yaml`.

## Pré-requisitos

- `Kubernetes` instalado
- `kubectl` instalado
- `Ingress Controller NGINX` instalado
- `cert-manager` instalado
- `ClusterIssuer` instalado

---

## Instalar o Nextcloud

```bash
git clone https://github.com/diegofnunesbr/nextcloud.git
cd nextcloud
kubectl apply -f applications/argocd-nextcloud.yaml
```

## Configurar o acesso local para o Nextcloud no Windows

```bash
echo "192.168.1.3 nextcloud.local" | sudo tee -a /mnt/c/Windows/System32/drivers/etc/hosts
```

## Acessar o Nextcloud

https://nextcloud.local/

## Remover o Nextcloud

```bash
kubectl delete -f applications/argocd-nextcloud.yaml
kubectl delete namespace nextcloud
```
