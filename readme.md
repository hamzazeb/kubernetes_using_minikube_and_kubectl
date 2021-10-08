# yaml files for deploying kubernetes cluster using minikube and kubectl


Adding current user to docker for allowing user to install minikube cluster:
	sudo usermod -aG docker $USER && newgrp docker

Starting a minikube cluster:
	minikube start --driver=docker

	kubectl get nodes
	minikube status


Basic kubectl commands:
	Make sure to install minikube and kubectl first
	kubectl get nodes
	kubectl get pods
	kubectl get services

creating components/pods
	kubectl create	deployment nginx-depl --image=nginx
	kubectl get deployment
	kubectl get pod
	kubectl get pod -o wide
	kubectl get replicaset
	kubectl get secret
	kubectl get all
	kubectl get all | grep mongodb
	kubectl edit deployment nginx-depl
	

for debugging
	kubectl logs nginx-depl-5c8bf76b5b-vs7qz (pod name)
	kubectl exec -it monge-depl-56bc67c6b6-m26bv -- bin/bash
	
	kubectl describe pod pod_name
	
	kubectl get deployment
	kubectl delete deployment mongo-depl
	
create yaml files for service and deployment
	kubectl apply -f nginx-deployment.yaml
	kubectl apply -f nginx-service.yaml
	
	kubectl describe service nginx-service
	kubectl get deployment nginx-deployment -o yaml > nginx-deployment-result.yaml
	
	
Minikube
	minikube service mongo-express-service >> it will assing a public ip address to a service
	
	
GET BASE64 OF ANY VALUE:
	echo -n 'hamza"PWD' | base64