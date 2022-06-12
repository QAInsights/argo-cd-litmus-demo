# Installing Argo CD

```
kubectl create namespace argocd 

kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Launching Argo CD

Use one of the following commands to launch Argo CD:

### Port Forwarding
```
kubectl port-forward svc/argocd-server -n argocd 8081:443
```

### LoadBalancer

```
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
```

## Get Password
```
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
```

## Login
```
argocd login --insecure <argo_cd_url:port> --username admin
```

## Change Password
```
argocd account update-password
```