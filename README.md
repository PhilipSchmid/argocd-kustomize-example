# Argo CD Kustomize Example

## Getting Started
1. Argo CD Login:
```bash
argocd login <argocd.your.k8s.cluster.example.com> --sso --grpc-web
```

2. Verify kustomizations:
```bash
kustomize build .
```

3. Create the app:
```bash
argocd app create argocd-kustomize-example-pschmid2 --repo https://github.com/philipschmid/argocd-kustomize-example.git --dest-server https://kubernetes.default.svc --path . --dest-namespace pitc-pschmid2-argocd
```

4. Sync app:
```bash
argocd app sync argocd-kustomize-example-pschmid2
argocd app get argocd-kustomize-example-pschmid2
```

## Credit
- https://github.com/argoproj/argocd-example-apps/tree/master/kustomize-guestbook