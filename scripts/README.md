# Script usage

1. start.py - `python start.sh -t {hyperledger_component}` to start create pods
2. stop.py - Opposite of start.py
3. setup-hyperledger.sh - Execute this after all of component running without failure
4. clean_pv.sh - To clean mounted volume from kubernetes
5. clear_container_dind.sh - DIND has been mapped volume to kubernetes master when need to deploy chaincode it need to clear first

## When minikube broken

Remove current minikube from virtualbox and `minikube delete` then try to `minikube start`

## Before start minikube

- Mount resources to master node `minikube mount ../hyperledger-prerequisite:/mnt/sda1/mounted`

## When chaincode container cannot start

Try to remove chaincode docker images inside minikube cluster access by `minikube ssh`

## Pull docker directly for chaincode container creation

In case of when cannot instantiate chaincode, try to pull base image for chaincode then try again `docker pull hyperledger/fabric-ccenv:latest`

## Enable ingress

`minikube addons enable ingress` follow: [Ingress Link](https://kubernetes.io/docs/tasks/access-application-cluster/ingress-minikube/)
