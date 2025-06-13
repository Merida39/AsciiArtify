# Proof of Concept: Демо-інструкція на отримання доступу до інтерфейсу ArgoCD

## Інструменти

- Kubernetes кластер: Kind
- GitOps система: ArgoCD

---

## Встановлення ArgoCD

### Створення неймспейсу

```bash
kubectl create namespace argocd
