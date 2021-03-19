```
kubectl -n kube-system get pods
kubectl -n kube-system get pods --watch
kind create cluster --config kind-config.yaml --name my-cluster
kubectl cluster-info --context kind-my-cluster
kubectl get nodes
helm repo add cilium https://helm.cilium.io/
docker pull cilium/cilium:v1.9.5
kind load docker-image cilium/cilium:v1.9.5
helm install cilium cilium/cilium --version 1.9.5 \\n   --namespace kube-system \\n   --set nodeinit.enabled=true \\n   --set kubeProxyReplacement=partial \\n   --set hostServices.enabled=false \\n   --set externalIPs.enabled=true \\n   --set nodePort.enabled=true \\n   --set hostPort.enabled=true \\n   --set bpf.masquerade=false \\n   --set image.pullPolicy=IfNotPresent \\n   --set ipam.mode=kubernetes
kubectl -n kube-system get pods --watch
```
## Helm Installation
```
helm repo add cilium https://helm.cilium.io/
kind load docker-image cilium/cilium:v1.9.5

helm install cilium cilium/cilium --version 1.9.5 \
   --namespace kube-system \
   --set nodeinit.enabled=true \
   --set kubeProxyReplacement=partial \
   --set hostServices.enabled=false \
   --set externalIPs.enabled=true \
   --set nodePort.enabled=true \
   --set hostPort.enabled=true \
   --set bpf.masquerade=false \
   --set image.pullPolicy=IfNotPresent \
   --set ipam.mode=kubernetes
```

## In case of error: `Unable to connect to the server: net/http: TLS handshake timeout`
# use: 
```
$ unset http_proxy
$ unset https_proxy
```
