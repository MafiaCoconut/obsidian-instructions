### Install link
https://www.virtono.com/community/tutorial-how-to/how-to-deploy-postgresql-on-k3s/

### Get password
```sh
export POSTGRES_PASSWORD=$(kubectl get secret --namespace default test-postgresql -o jsonpath="{.data.postgres-password}" | base64 -d)
```

### Connect to Database
From device
```sh
kubectl run test-postgresql-client --rm --tty -i --restart='Never' --namespace default --image docker.io/bitnami/postgresql:17.5.0-debian-12-r18 --env="PGPASSWORD=$POSTGRES_PASSWORD" \
      --command -- psql --host test-postgresql -U postgres -d postgres -p 5432
```

From outerworld
```sh
kubectl port-forward --namespace default svc/test-postgresql 5432:5432 &
    PGPASSWORD="$POSTGRES_PASSWORD" psql --host 127.0.0.1 -U postgres -d postgres -p 5432
```
