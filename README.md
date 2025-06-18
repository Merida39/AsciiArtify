# 🚀 AsciiArtify — DevOps Documentation

👋 Ласкаво просимо до DevOps-документації проєкту **AsciiArtify**.  
Цей репозиторій демонструє PoC-реалізацію GitOps-інфраструктури для стартапу, який планує створити сервіс ASCII-art перетворення зображень за допомогою ML.

---

## 📌 Мета

- Перевірити можливість використання Kubernetes + GitOps на основі ArgoCD.
- Налаштувати повний CI/CD цикл з відстеженням змін у Git.
- Продемонструвати функціональність деплоювання додатку через ArgoCD.

---

## 🗂️ Документація

| Етап | Файл | Опис |
|------|------|------|
| 🔹 Concept | [`doc/Concept.md`](doc/Concept.md) | Порівняльний аналіз Minikube, Kind, k3d. Рекомендація: **Kind**. |
| 🔹 PoC | [`doc/POC.md`](doc/POC.md) | Розгортання ArgoCD в кластері Kind, доступ до UI. |
| 🔹 MVP | [`doc/MVP.md`](doc/MVP.md) | GitOps деплой: автоматичне застосування змін із Git. |

---

## 🎬 Демо

| Етап | Файл | Опис |
|------|------|------|
| Concept | [`demo/demo.gif`](demo/demo.gif) | Розгортання Hello World у Kind. |
| PoC | [`demo/demo-argocd.gif`](demo/demo-argocd.gif) | Встановлення та доступ до ArgoCD UI. |
| MVP | [`demo/go-demo-app.gif`](demo/go-demo-app.gif) | Автоматичний деплой із репозиторію `go-demo-app`. |

---

## 🧩 Інструменти

- Kubernetes (Kind)
- ArgoCD
- GitHub
- Kubectl, Docker, VSCode

---

## 🧠 Автор

**DevOps інженер:** [Merida39](https://github.com/Merida39)

Цей репозиторій є результатом виконання завдань в рамках навчальної програми **SoftServe IT Academy — DevOps**.

---

## 🚀 Старт

```bash
# Створення кластера
kind create cluster --name asciiartify

# Встановлення ArgoCD
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Port-forward для доступу до UI
kubectl port-forward svc/argocd-server -n argocd 8080:443

# Вхід: http://localhost:8080
# Логін: admin
# Пароль: (виводиться з секрету)
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 --decode
