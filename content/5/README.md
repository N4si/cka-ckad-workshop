### Service

You are tasked with exposing the frontend deployment using a NodePort service on port 30004. 

**Question:**

You have deployed an Nginx application named `frontend` in the `kcd` namespace with specific parameters. Now, you are required to expose this deployment using a NodePort service on port 30004. How would you accomplish this?

**Answer:**

To expose the `frontend` deployment with a NodePort service on port 30004, you can follow these steps:

<details>
<summary>Click to reveal solution</summary>

## Solution:

1. Create a NodePort service to expose the `frontend` deployment on port 30004:
   ```bash
   kubectl expose deployment frontend --type=NodePort --port=8080 --target-port=8080 --namespace=kcd --name=frontend-service --node-port=30004
   ```

This command creates a NodePort service named `frontend-service` in the `kcd` namespace, exposing the `frontend` deployment on port 30004. The service forwards traffic to the pods on port 8080, where the Nginx application is running.

This approach allows you to expose the `frontend` deployment with a NodePort service on port 30004 for external access.

</details>

Feel free to use this question and answer in your documentation. Let me know if you need further assistance!
