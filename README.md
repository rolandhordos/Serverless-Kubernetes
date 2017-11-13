# Serverless on Kubernetes
## via Kubeless

Project aims to document and demonstrate a path of study and experience gained setting up and running Kubernetes, Kubeless, and Serverless.

[Serverless - Kubeless - Kubernetes](https://yuml.me/rolandhordos/diagram/scruffy;dir:TB/class/[%20Serverless%20%7C%20-%20cloud%20code%20anywhere%20]%20-%20[%20Kubeless%20%7C%20-%20brings%20serverless%20to%20k8s%20],%20[%20Kubeless%20]%20-%20[%20Kubernetes%20%7C%20-%20move%20your%20cloud%20anywhere%20])

## Quick Connects

Precondition - k8s running
	
	minikube start

### Dashboard

	minikube dashboard

### Shell

	kubectl exec $POD_NAME -ti bash

## Bootcamp Training

Straightforward high quality [Kubernetes training materials](https://kubernetes.io/docs/tutorials/kubernetes-basics/deploy-intro/)

## Dev Server

### Local Mac

#### MiniKube - Running in 5 Enter Keys on 2012 MBP

##### Installation

	brew cask install minikube
  	brew install docker-machine-driver-xhyve
  	sudo chown root:wheel /usr/local/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
	sudo chmod u+s /usr/local/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve

##### First Start

	minikube start --vm-driver=xhyve
	
It will download a ~140M ISO, work for a while then voila !

##### Checking Status

	minikube status
	
##### Dashboard

	minikube dashboard	


## RoadMap

Adding Kubeless to Minikube

Supporting Bootcamp with a Service

Stateful Sets - Add a Store



## Landfill

#### Kube Solo (dropped - unmaintained - does not install)

Initially optimistic as the Kubernetes Dies team has contributed so much including this tool.  Then came the acq by Microsoft, so how much macOS tooling will be maintained ..

Works with the macOS user space Hypervisor.framework that does not require heavy virtualization tools.

##### Installation

	brew install libev
	
Download and Install [CoreCtl dmg](https://github.com/TheNewNormal/corectl.app/releases/download/v0.2.9/corectl_v0.2.9.dmg)

Download and Install [Kube Solo dmg](https://github.com/TheNewNormal/kube-solo-osx/releases/download/v1.0.3/Kube-Solo_v1.0.3.dmg)

***FAILED HERE*** - would not install with an error code -43 - gatekeeper would not let it install.  Comments blame it on needing a newer version of CoreCtl.  Buubye !
