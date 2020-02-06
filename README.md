# wordpress-kubernetes
This is a kubernetes implementation of Wordpress on a single node cluster


# Design as per the Requirements
`
1) LoadBalancer : Created by Service on Kubernetes which loadbalances the wordpress instances. here it is only one instance, if the replicas are more than it automatically loadbalances all the replicas
`
## How to Run/Execute

### Pre-Requisites

1) Kubernetes locally using minikube or any other kubernetes flavour and  you can run the same on any cloud provider.

## Install Minikube 
Ref: https://kubernetes.io/docs/setup/learning-environment/minikube/
Note: Minikube takes virtual box as its hypervisor.

## How to Run

#### Create a Secret my-pass using the below comand.
`
kubectl create secret generic mysql-pass --from-literal=password=123456
`
#### Run the mysql-deployment.yaml
` kubectl apply -f mysql-deployment.yaml `

#### Run the wordpress-deployment.yaml
` kubectl apply -f wordpress-deployment.yaml `

#### You can view the dashboard using the below command
` minikube dashboard`

#### Run the command to get the URL exposed by minikube(kubernetes)
minikube service wordpress --url

