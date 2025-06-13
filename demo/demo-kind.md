
---

# 📄 **demo/demo-kind.md** (сценарій для демо)

```markdown
# Демонстрація роботи з Kind

## Підготовка

- Операційна система: Linux / Mac / Windows
- Docker: встановлений
- Kubectl: встановлений

## Крок 1 — Встановлення Kind

```bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.22.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
