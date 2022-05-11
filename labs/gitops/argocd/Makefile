
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

.PHONY: get-admin-password
get-admin-password:
	kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo