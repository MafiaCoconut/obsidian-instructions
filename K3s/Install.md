Main link
https://maxdon.tech/posts/k3s-raspberry-pi/?utm_source=chatgpt.com

But important to run install command like this and skip punkt 3.
```sh
curl -sfL https://get.k3s.io | K3S_TOKEN=$K3S_TOKEN sh -s - server \
  --write-kubeconfig-mode '0644' \
  --disable 'servicelb' --disable 'traefik' \
  --kube-controller-manager-arg 'bind-address=0.0.0.0' --kube-proxy-arg 'metrics-bind-address=0.0.0.0' \
  --kube-scheduler-arg 'bind-address=0.0.0.0' \
  --kube-controller-manager-arg 'terminated-pod-gc-threshold=10'
```

