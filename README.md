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

#### Kubeless

Create the namespace it needs first, applying the Yaml file found in Kubeless folder in this repo.

	kubectl create -f ./create-kubeless-namespace.yaml 
	
Use the dashboard to confirm the namespace is ready.  Then install kubeless itself.

	brew install kubeless/tap/kubeless
	
Pay attention to what the installation says.  In this case it wanted the following to be executed.

	`curl -sL https://github.com/kubeless/kubeless/releases/download/v0.2.3/kubeless-v0.2.3.yaml | kubectl create -f -`

It took a few minutes before all pieces were ready, made easy to monitor with the dashboard.


## RoadMap

Adding Kubeless to Minikube

Adding Serverless to Kubeless

Serverless Stack Tutorial
	- [Server](https://github.com/AnomalyInnovations/serverless-stack-demo-api)
	- [Client](https://github.com/AnomalyInnovations/serverless-stack-demo-client)

[React Isomorphic Rendering](https://github.com/TylorShin/react-universal-in-serverless)

Supporting Node App with a Service

Stateful Sets - Add a Store

Kafka Queue



## Landfill

#### Kube Solo (dropped - unmaintained - does not install)

Initially optimistic as the Kubernetes Dies team has contributed so much including this tool.  Then came the acq by Microsoft, so how much macOS tooling will be maintained ..

Works with the macOS user space Hypervisor.framework that does not require heavy virtualization tools.

##### Installation

	brew install libev
	
Download and Install [CoreCtl dmg](https://github.com/TheNewNormal/corectl.app/releases/download/v0.2.9/corectl_v0.2.9.dmg)

Download and Install [Kube Solo dmg](https://github.com/TheNewNormal/kube-solo-osx/releases/download/v1.0.3/Kube-Solo_v1.0.3.dmg)

***FAILED HERE*** - would not install with an error code -43 - gatekeeper would not let it install.  Comments blame it on needing a newer version of CoreCtl.  Buubye !
