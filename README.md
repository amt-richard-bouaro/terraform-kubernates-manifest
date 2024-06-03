### eks_connect
```sh

aws eks --region eu-west-1 update-kubeconfig --name main-eks-cluster

```

### argocd_initial_admin_secret

```sh

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath=\"{.data.password}\" | base64 -d

```

### argocd_server_url

```sh
kubectl get svc argocd-server -n argocd -o json | jq --raw-output '.status.loadBalancer.ingress[0].hostname'

```