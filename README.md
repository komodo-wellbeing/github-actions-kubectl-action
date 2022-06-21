# github-actions-kubectl-action

GitHub Action to manage a K8s (Kubernetes) cluster using kubectl.

# Usage

To use this action, add the following step to your GitHub Action workflow:

```yaml
- uses: komodo-wellbeing/github-actions-kubectl-action@v1
```

It's also possible to specify the version of the [kubectl](https://kubernetes.io/docs/reference/kubectl/) CLI to use.
The current default release used by this action is `v1.24.0`.

```yaml
- uses: komodo-wellbeing/github-actions-kubectl-action@v1
  with:
    kubectl-version: v1.24.0
```

Once you've completed this setup, the `kubectl` binary is available to use in subsequent steps.

```yaml
name: Kubectl Action

on:
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: komodo-wellbeing/github-actions-kubectl-action@v1
      - run: kubectl get pods
```
