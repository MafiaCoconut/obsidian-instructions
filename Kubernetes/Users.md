
### Create service account with token credentials
1. Config file
```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: k3s-test-user
  namespace: kube-system
---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: k3s-test-user-binding
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
- kind: ServiceAccount
  name: k3s-test-user
  namespace: kube-system
```

2. Open container
```
docker exec -it k3d-k3s-test-server-0 sh`
```

3. 
```
cat <<EOF | kubectl apply -f -
<Paste from config file>
EOF
```

4. Get name of secret
```
kubectl -n kube-system get secret | grep api-user
```

5. Get token
```
kubectl -n kube-system get secret api-user-token-abcde -o jsonpath="{.data.token}" | base64 -d
```

6. Set in kubeconfig 
```
users:
- name: api-user
	user:
		token: <token>
```