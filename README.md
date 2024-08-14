# bitcoin-core-kubernetes
Configs for running BitCoin full node in Kubernetes

[Step-by-step kubectl commands](https://coderise.io/running-bitcoin-core-in-kubernetes-azure-container-service-cluster/)

Useful commands:

Deployment
- `kubectl create -f manifests/<FILE_NAME>.yml`
- `kubectl delete -f manifests/<FILE_NAME>.yml`

General
- `kubectl get all -n bitcoin`
- `kubectl get pvc -n bitcoin`
- `kubectl get pv`

Specific
- `export PODNAME=$(kubectl get pods -o wide -n bitcoin | grep bitcoin | awk '{print $1}')`
- `kubectl describe pod -n bitcoin $PODNAME`
- `kubectl exec -it -n bitcoin $PODNAME -- bash`
- > `gosu bitcoin bash`
- > `bitcoin-cli getmininginfo`
- > `bitcoin-cli getwalletinfo` (NOTE: need to create as wallets are not created by default)
- > `bitcoin-cli listreceivedbyaddress 1 true`

[`bitcoin-cli` Reference](https://developer.bitcoin.org/reference/rpc/)