### RBAC
Context -
You have been asked to create a new ClusterRole for a deployment pipeline and bind it to a specific ServiceAccount scoped to a specific namespace.

Task -
Create a new ClusterRole named deployment-clusterrole, which only allows to create the following resource types:
✑ Deployment
✑ Stateful Set
✑ DaemonSet
Create a new ServiceAccount named cicd-token in the existing namespace app-team1.
Bind the new ClusterRole deployment-clusterrole to the new ServiceAccount cicd-token, limited to the namespace app-team1.


**Answer:**

<details>
<summary>Click to reveal solution</summary>

```markdown
### RBAC

**Context:**
You have been asked to create a new ClusterRole for a deployment pipeline and bind it to a specific ServiceAccount scoped to a specific namespace.

**Task:**

1. **Create a new ClusterRole**:
   ```bash
   kubectl create clusterrole deployment-clusterrole --verb=create --resource=deployments,statefulsets,daemonsets
   ```

2. **Create a new ServiceAccount**:
   ```bash
   kubectl create serviceaccount cicd-token -n app-team1
   ```

3. **Bind the ClusterRole to the ServiceAccount**:
   ```bash
   kubectl create rolebinding deployment-binding --clusterrole=deployment-clusterrole --serviceaccount=app-team1:cicd-token -n app-team1
   ```

4. **Test the role and actions**:
   ```bash
   kubectl auth can-i create deployment --as=system:serviceaccount:app-team1:cicd-token -n app-team1
   ```

</details>