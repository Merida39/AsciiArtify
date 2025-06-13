# MVP: Налаштування розгортання продукту через ArgoCD

## Інструменти

- Kubernetes кластер: Kind
- GitOps система: ArgoCD

---

## Налаштування ArgoCD для розгортання

### Створення додатку в ArgoCD

- **Application Name**: `go-demo-app`
- **Project**: `default`
- **Sync Policy**: `Automatic`
- **Repository URL**: `https://github.com/den-vasyliev/go-demo-app`
- **Revision**: `HEAD`
- **Path**: `.`
- **Cluster**: `https://kubernetes.default.svc`
- **Namespace**: `default`

---

## Перевірка розгортання

Перевірити, що додаток задеплоївся:

```bash
kubectl get pods
kubectl get svc