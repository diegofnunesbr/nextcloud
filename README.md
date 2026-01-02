# Nextcloud

Este guia descreve o deployment do **Nextcloud** com banco **MariaDB** em um cluster Kubernetes, utilizando o manifesto `nextcloud.yaml`.

## Pré-requisitos

- `Kubernetes` instalado
- `Ingress Controller NGINX` instalado
- `cert-manager` instalado
- `ClusterIssuer` criado com o nome `selfsigned`
- IP `192.168.15.7` disponível na rede

---

## Instalação

1. **Aplique o manifesto no cluster:**

```bash
kubectl apply -f nextcloud.yaml
