# Proof of Concept: Демо-інструкція на отримання доступу до інтерфейсу ArgoCD

## Інструменти

- Kubernetes кластер: Kind
- GitOps система: ArgoCD

---

Документ описує етап Proof of Concept, де:

створено кластер Kubernetes (Kind),

встановлено ArgoCD в namespace argocd,

налаштовано доступ до Web UI через port-forward,

отримано логін/пароль для входу в ArgoCD,

додано демонстрацію (GIF) з процесом встановлення.

Мета — перевірити можливість GitOps-деплойменту через ArgoCD у локальному середовищі.

### Створення неймспейсу

```bash
kubectl create namespace argocd
