### ETCD Backup

Create a snapshot of the existing etcd instance running at https://127.0.0.1:2379, saving the snapshot to /var/lib/backup/etcd-snapshot.db.


**Answer:**

<details>
<summary>Click to reveal solution</summary>

```bash
cat /etc/kubernetes/manifests/etcd.yaml | grep file

# Insert the values in the below command
ETCDCTL_API=3 etcdctl --endpoints=https://127.0.0.1:2379 \
  --cacert=<trusted-ca-file> --cert=<cert-file> --key=<key-file> \
  snapshot save <backup-file-location>

</details>