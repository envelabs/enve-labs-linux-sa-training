# kubectl commands

#### view cluster info
```
kubectl config view
```

#### define cluster config profile
```
kubectl --kubeconfig ~/.kube/config-<param> get pods
```

#### define user/cluster
```
kubectl config set-credentials admin/<api-cluster-url> --username=<user> --password=<passwd>
```

#### define cluster  
```
kubectl config set-cluster <api-cluster-url> --server=https://<api-cluster-url> --insecure-skip-tls-verify=true
```

#### create context
```
kubectl config set-context default/<api-cluster-url>/admin --user=admin/<api-cluster-url> --namespace=default --cluster=<api-cluster-url>
```

#### define context to use
```
kubectl config use-context default/<api-cluster-url>/admin
```

#### check cluster status
```
kubectl get nodes
```

#### check deployments
```
kubectl get deployments
```

#### log into the registry
```
kubectl create secret docker-registry credentials --docker-server https://index.docker.io/v1/ --docker-username=<docker-hub-user> --docker-password=<docker-hub-passwd> --docker-email=<docker-hub-user-email>
```

#### patch service account to pull private images
```
kubectl patch serviceaccount default -p '{"imagePullSecrets": [{"name": "credentials"}]}'
```

#### get docker image hash
```
docker inspect --format='{{index .RepoDigests 0}}' <image-id>
```

#### get image hash
```
kubectl get pod <pod> -o json | jq '.status.containerStatuses[] | { "image": .image, "imageID": .imageID }'
```

#### expose application deployment
```
kubectl expose deployment <deployment-id> --port=<port> --target-port=<port> --type=LoadBalancer
````

#### list services exposed
```
kubectl describe services <deployment-id>
```

#### list services
```
kubectl get services -o wide
```

#### remove service
```
kubectl delete service <service>
```

#### check port in the pod
```
kubectl get pods <pod> --template='{{(index (index .spec.containers 0).ports 0).containerPort}}{{"\n"}}'
```

#### check pods status
```
kubectl get pods
```

#### check pods by namespace
```
kubectl --namespace <namespace> get pod
```

#### delete pods
```
kubectl delete pods --all
```

#### delete deployment
```
kubectl delete deployment <deployment>
```

#### get logs
```
kubectl logs <pod>

kubectl --namespace <namespace> logs <pod>
```
