# MVP: Налаштування розгортання продукту через ArgoCD

## Інструменти

- Kubernetes кластер: Kind
- GitOps система: ArgoCD

---
На цьому етапі налаштовується повний цикл CI/CD за допомогою ArgoCD:

створено застосунок у ArgoCD, що стежить за репозиторієм go-demo-app,

ArgoCD автоматично синхронізує стан кластеру з Git,

при зміні у Git (наприклад, версія імеджу) — зміни автоматично застосовуються в Kubernetes.

GIF‑демонстрація ілюструє, як ArgoCD виявляє новий комміт і оновлює кластер без ручного втручання.

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