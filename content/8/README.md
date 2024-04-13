### ingress

Task -
Create a new nginx Ingress resource as follows:
✑ Name: pong
✑ Namespace: ing-internal
✑ Exposing service hello on path /hello using service port 5678

```markdown
### Ingress

<details>
<summary>Click to reveal YAML</summary>

```yaml
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: minimal-ingress
  annotations:
    nginx.ingress.kubernetes.io/rewrite-target: /
spec:
  ingressClassName: nginx-example
  rules:
  - http:
      paths:
      - path: /testpath
        pathType: Prefix
        backend:
          service:
            name: test
            port:
              number: 80
```

</details>

<details>
<summary>Explanation</summary>

This Ingress configuration creates a minimal nginx Ingress named `minimal-ingress`. It forwards traffic from the path `/testpath` to the `test` service on port 80. The `nginx.ingress.kubernetes.io/rewrite-target` annotation is used to rewrite the path before forwarding it to the backend service. The `ingressClassName` specifies the class name of the Ingress controller.

</details>
```

