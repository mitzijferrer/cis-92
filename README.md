# CIS-92 Project

**Author:** Mitzi Ferrer

## 1. Environment Variables

The environment variables that are in `config.yaml` and `secret.yaml`:

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


## 2. Deploy Kubernetes Cluster

- To deploy the application to your active Kubernetes cluster, 
run the command in a terminal:

```bash
kubectl apply -f deployment/
```

## 3. Delete Application

- To delete the application and its resources from the cluster, 
run the command:

```bash
kubectl delete -f deployment/
```
