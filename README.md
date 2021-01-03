## introduction :
Local MongoDB and Express server setup using `minikube` and `kubernetes` .

## setup :
Here i have used `Kubernetes` as platform and minikube as tool to spin up the cluster in local environment .

## Running :
```$ minikube start```

* Set username and password for MongoDB Database and that should be base64 because we are using `k8s` `secrets` .
```
$echo -n 'admin' | base64
$echo -n 'pass' | base64
```

* Maintain the ordering :
```$ kubectl apply -f mongo-secret.yml```
```$ kubectl apply -f mongo-depl.yaml```
```$ kubectl apply -f mongo-config.yaml```
```$ kubectl apply -f mongo-express.yaml```
```$ kubectl get pod ```
```$ kubectl logs mongo-express-(some number)```

```
| Now You Can See The Server Is Running Message |
```

* Exposing our service to external `URL` we have user `loadbalancer type`(Here) :
```
$ kubectl get service
$ minikube service mongo-express-service
```
