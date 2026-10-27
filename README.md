# mini-task-manager-charts

Helm-чарти для [mini-task-manager](https://github.com/SilentProg/mini-task-manager) (ЛР3, Argo CD).

- `charts/mini-task-manager` — застосунок + MySQL + Ingress з сертифікатом Let's Encrypt.
- `image.tag` у `values.yaml` оновлює CI-пайплайн репозиторію mini-task-manager після кожної збірки образу.
- Workflow `Release Charts` (helm/chart-releaser-action) публікує кожну нову версію чарту в GitHub Releases
  і в Helm-репозиторій на GitHub Pages:

```
helm repo add mtm https://silentprog.github.io/mini-task-manager-charts
helm search repo mtm --versions
```

Argo CD стежить за `charts/mini-task-manager` у гілці `main` з автоматичною синхронізацією.
