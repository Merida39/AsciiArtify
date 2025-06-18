# Proof of Concept: Демо-інструкція на отримання доступу до інтерфейсу ArgoCD

## Інструменти

- Kubernetes кластер: Kind
- GitOps система: ArgoCD

---

## Встановлення ArgoCD

### Створення неймспейсу

```bash
kubectl create namespace argocd


## Результат

- ArgoCD успішно встановлено в кластер Kind
- Веб-інтерфейс працює: http://localhost:8080
- Отримано логін і пароль адміністратора
- Система готова до розгортання MVP через GitOps