### Deployment

Task:
Create a new deployment for running.nginx with the following parameters;

-Run the deployment in the kcd namespace. 
-Name the deployment frontend and configure with 4 replicas
-Configure the pod with a container image of lfccncf/nginx:1.13.7
-Set an environment variable of NGINX__PORT=8080 and also expose that port for the container above

**Answer:**

To create a new deployment for running Nginx with the specified parameters, you can follow these steps:

<details>
<summary>Solution</summary>

## Solution:

1. Create the deployment named `frontend` with 4 replicas, using the container image `lfccncf/nginx:1.13.7`, and set an environment variable `NGINX_PORT` to `8080`:
   ```bash
   kubectl create deployment frontend --image=lfccncf/nginx:1.13.7 --replicas=4 --namespace=kcd --env="NGINX_PORT=8080"

This will create a deployment named frontend in the kcd namespace, with 4 replicas running the Nginx container image lfccncf/nginx:1.13.7. The environment variable NGINX_PORT will be set to 8080 in each pod, and port 8080 will be exposed for external access.

This approach allows you to create a deployment for running Nginx with the specified parameters in Kubernetes.

</details>
```