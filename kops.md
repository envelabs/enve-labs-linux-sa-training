# Kops - Kubernetes Operations
Kops is a Kubernetes cluster tool used to orchestrate the applications deployment against the cloud

### Cluster config

#### connecting to the K8s cluster
load AWS credentials
```
export AWS_PROFILE=<profile-name>
```

#### set up access to cluster for the first time
Edit cluster config, add your IP to kubernetesApiAccess and sshAccess to allow TCP 443 from your IP. Update cluster and confirm update

#### common kops parameters
`state`: S3 bucket name where Kops stores its configuration</br>
`cluster-name`: cluster name</br>
`namespace`: brand

#### export kubectl config
```
kops --state s3://<aws-s3-bucket> export kubecfg --name <cluster-name>
```

#### validate a cluster
```
kops --state s3://<aws-s3-bucket> --name <k8s.brand.dnszone> validate cluster
```

#### cluster update
```
kops --state s3://<aws-s3-bucket> --name <k8s.brand.dnszone> --lifecycle-overrides 'IAMRole=ExistsAndWarnIfChanges,IAMRolePolicy=ExistsAndWarnIfChanges,IAMInstanceProfileRole=ExistsAndWarnIfChanges' update cluster
```

#### confirm an update procedure
```
kops --state s3://<aws-s3-bucket> --name <k8s.brand.dnszone> --lifecycle-overrides 'IAMRole=ExistsAndWarnIfChanges,IAMRolePolicy=ExistsAndWarnIfChanges,IAMInstanceProfileRole=ExistsAndWarnIfChanges' update cluster --yes
```

#### edit cluster configuration
```
kops --state s3://<aws-s3-bucket> --name <k8s.brand.dnszone> edit cluster
```

### Kubectl commands

#### list running pods
```
kubectl -n namespace get pods
```

#### get logs
```
kubectl -n namespace logs pod_name
```

#### list deployments
```
kubectl -n namespace get deployments
```

#### edit a deployment
```
kubectl -n namespace edit deployment deployment_name
```

#### list secrets
```
kubectl -n namespace get secrets
```

#### show contents of a secret
```
kubectl -n namespace get secrets secret_name -o yaml
```
