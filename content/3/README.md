### Logging

You are tasked with storing the logs of the Redis cache pod in a file named logs.txt


## Task:

To store the logs of the Redis cache pod in a file named `logs.txt`, you can use the `kubectl logs` command to fetch the logs of the pod and redirect the output to a file. Follow these steps:

<details>
<summary>Solution</summary>

## Solution:


1. Identify the name of the Redis cache pod:
   ```bash
   kubectl get pods -n web
   ```
   Note down the name of the Redis cache pod, let's say it's named `cache`.

2. Use the `kubectl logs` command to fetch the logs of the `cache` pod and redirect the output to a file named `logs.txt`:
   ```bash
   kubectl logs -n web cache > logs.txt
   ```

This command fetches the logs of the `cache` pod in the `web` namespace and redirects the output to a file named `logs.txt`. You can then view the contents of `logs.txt` using any text editor or command-line utility.

This approach allows you to store the logs of the Redis cache pod in a file for later analysis or debugging purposes.
```