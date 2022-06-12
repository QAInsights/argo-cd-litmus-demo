# Installing LitmusChaos

```
kubectl create namespace litmus 

kubectl apply -f https://raw.githubusercontent.com/litmuschaos/litmus/master/mkdocs/docs/2.9.0/litmus-2.9.0.yaml
```

## Patch

```
kubectl patch svc litmusportal-frontend-service -p '{"spec": {"type": "LoadBalancer"}}' -n litmus
```

```
kubectl patch svc litmusportal-server-service -p '{"spec": {"type": "LoadBalancer"}}' -n litmus
```