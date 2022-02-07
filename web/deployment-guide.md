1. Test django

```
python manage.py test
```

2. Build container

```
docker build -f Dockerfile \
  -t registry.digitalocean.com/cfe-k8s/django-k8s-web:latest 
  -t registry.digitalocean.com/cfe-k8s/django-k8s-web:v1 
```

3. Push Container with 2 tags: latest and random

```
docker push registry.digitalocean.com/cfe-k8s/django-k8s-web --all-tags
```

4. Update secrets (if needed)

```
kubectl delete secret django-k8s-web-prod-env
kubectl create secret generic django-k8s-web-prod-env --from-env-file=web/.env.prod

```

5. Update Deployment `k8s/apps/django-k8s-web.yaml`:

Add in a rollout strategy:


`imagePullPolicy: Always`

CHange 
```
image: registry.digitalocean.com/cfe-k8s/django-k8s-web:latest
```
to

```
image: registry.digitalocean.com/cfe-k8s/django-k8s-web:v1 
```
Notice that we need `v1` to change over time.


```
kubectl apply -f k8s/apps/django-k8s-web.yaml
```

6. Roll Update:
```
kubectl rollout status deployment/django-k8s-web-deployment
```
7. Migrate database

Get a single pod (either method works)

```
export SINGLE_POD_NAME=$(kubectl get pod -l app=django-k8s-web-deployment -o jsonpath="{.items[0].metadata.name}")
```
or 
```
export SINGLE_POD_NAME=$(kubectl get pod -l=app=django-k8s-web-deployment -o NAME | tail -n 1)
```

Then run `migrate.sh` 

```
kubectl exec -it $SINGLE_POD_NAME -- bash /app/migrate.sh
```