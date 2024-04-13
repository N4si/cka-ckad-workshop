# Web Application Redis Cache Pod

A web application requires a specific version of Redis to be used as a cache. This README provides instructions on how to create a pod with the following characteristics:

- The pod must run in the **web** namespace.
- The name of the pod should be **cache**.
- Use the **Ifccncf/redis** image with the **3.2** tag.
- Expose port **6379**.

## Task:

Create a pod with the specified characteristics and leave it running when complete.

<details>
<summary>Solution</summary>

## Solution:

Follow the steps below to complete the task:

### Step 1: Create Redis Pod
```bash
kubectl run cache --image=Ifccncf/redis:3.2 --port=6379 --namespace=web

### Step 2: Verify the Pod
```bash
kubectl get pods -n web

### Expected Output:
The output should display the created pod named cache in the web namespace.

Example:

NAME    READY   STATUS    RESTARTS   AGE
cache   1/1     Running   0          5s
</details>