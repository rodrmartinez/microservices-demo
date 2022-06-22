
.PHONY: kind-create
kind-create:
	kind create cluster --name=cre-labs-argo-workflows

.PHONY: kind-delete
kind-delete:
	kind delete cluster --name=cre-labs-argo-workflows

.PHONY: config-github
config-github:
 export GITHUB_TOKEN=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	&\
 export GITHUB_USER=rodrmartinez

.PHONY: install-argo-workflows
install-argo-workflows:
	kubectl create ns argo &\
	kubectl apply -n argo -f https://raw.githubusercontent.com/argoproj/argo-workflows/master/manifests/quick-start-postgres.yaml

.PHONY: install-minio
install-minio:
	helm repo add minio https://helm.min.io/ # official minio Helm charts &&\
	helm repo update &&\
	helm install argo-artifacts minio/minio --set service.type=LoadBalancer --set fullnameOverride=argo-artifacts
