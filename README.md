# CIS-92 Project

**Author:** Mitzi Ferrer

## 1. Environment Variables

- The environment variables that are in `config.yaml` and `secret.yaml`:

| Variable Name | Default Value | Description |
| --- | --- | --- |
| PORT | `8080` | The port number the application listens on |
| STUDENT_NAME | `Mitzi Ferrer` | Name of the developer |
| SITE_NAME | `www.mitziferrer.com` | Domain name for the website |
| DATA_DIR | `/data` | Directory for storing data |
| DEBUG | `1` | Enables debug mode |
| SECRET_KEY| `*` | Base64-encoded Django secret key |
| DJANGO_SUPERUSER_NAME | `c3R1ZGVudA==` | Base64-encoded admin username | 
| DJANGO_SUPERUSER_EMAIL | `c3R1ZGVudEBzdHVkZW50LmNvbQ==` | Base64-encoded admin email |
| DJANGO_SUPERUSER_PASSWORD | `c3R1ZGVudA==` | Base64-encoded admin password|


- Environment variables that are in `values-postgres.yaml`:

| Variable Name | Default Value | Description |
| --- | --- | --- |
| username | `mysiteuser` | The database administrator username |
| password | `this-is-a-bad-password` | The password for the database user |
| database | `mysite` | The name of the database |
| memory | `1024Mi` | The maximum amount of RAM allocated to the container |
| cpu | `2000m` | The amount of CPU cores reserved for the container |
| ephemeral-storage | `100Mi` | The limit for temporary data stored on the local node |

## 2. Deploy Kubernetes Cluster

- To deploy the application to your active Kubernetes cluster, 
run the commands in a terminal:

```bash
helm install postgres oci://registry-1.docker.io/bitnamicharts/postgresql --values values-postgres.yaml
```
```bash
kubectl apply -f deployment/
```

## 3. Delete Application

- To stop the application but keep the data, run the commands:
```bash
kubectl delete -f deployment/
```
```bash
helm uninstall postgres
```

- To delete the data and reset the database, run the command:

```bash
kubectl delete pvc data-postgres-postgresql-0 
```