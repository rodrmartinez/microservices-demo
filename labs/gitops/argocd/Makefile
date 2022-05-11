
.PHONY: kind-create
kind-create:
	kind create cluster --name=cre-labs-argocd

.PHONY: kind-delete
kind-delete:
	kind delete cluster --name=cre-labs-argocd

.PHONY: install-argocd
install-argocd: 
	kubectl create namespace argocd &&\
	kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

.PHONY: create-microservices-demo-app
create-microservices-demo-app:
	argocd app create microservices-demo --repo https://github.com/rodrmartinez/microservices-demo.git --path release --dest-server https://kubernetes.default.svc --dest-namespace default