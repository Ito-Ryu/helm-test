# helm-test

## Authentication with Google Cloud
1. Login to Google Cloud
```
gcloud auth login
gcloud auth application-default login
```
2. Set Account and Project
```
gcloud config set account <ACCOUNT_NAME>
gcloud config set project <PROJECT_ID>
```

## Authenticate with GKE Cluster
1. List GKE Clusters
```
gcloud container clusters list
```

2. Get Cluster Credentials
```
gcloud container clusters get-credentials <CLUSTER_NAME> --project=<PROJECT_ID> --zone=<CLUSTER_ZONE(LOCATION)>
```

## Install Helm Charts
1. Create Namespace
```
kubectl create ns helm-test
```

2. Install Charts
```
helm install -n <NAMESPACE> <RELEASE_NAME> -f <VALUES_FILE> <CHART_NAME>
```

Example
```
helm install -n helm-test service1 -f service1/values.yaml ./service1

helm install -n helm-test service2 -f service2/values.yaml ./service2
```

## Uninstall Helm Releases
```
helm uninstall <RELEASE_NAME> -n <NAMESPACE>
```

Example
```
helm uninstall service1 -n helm-test

helm uninstall service2 -n helm-test
```