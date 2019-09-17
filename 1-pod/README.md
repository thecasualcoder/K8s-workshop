## Create a Pod

```bash
kubectl apply -f https://raw.githubusercontent.com/thecasualcoder/k8s-workshop/master/1-pod/pod.yaml
```

## Create a ReplicaSet

```bash
kubectl apply -f https://raw.githubusercontent.com/thecasualcoder/k8s-workshop/master/1-pod/replica-set.yaml
```

## Create a Deployment

> Delete the older replicaset, before continuing.

```bash
kubectl delete rs/dobby
kubectl apply -f https://raw.githubusercontent.com/thecasualcoder/k8s-workshop/master/1-pod/deployment.yaml
```

## View your pods

To view all the pods of dobby with their IPs

```bash
$ kubectl get pods -l app=dobby -o=custom-columns="NAME:.metadata.name,STATUS:.status.phase,POD_IP:.status.podIP"
```

## Watch changes happening during upgrades

```bash
kubectl get rs -l app=dobby -w

watch 'kubectl get rs -l app=dobby'
```