
.PHONY: kind-create
kind-create:
	./kind_registry.sh

.PHONY: kind-delete
kind-delete:
	kind delete cluster --name=cre-labs-tekton

.PHONY: install-tekton-all
install-tekton-all: install-tekton install-task-git-clone install-task-kaniko

.PHONY: install-tekton
install-tekton:
	kubectl apply --filename https://storage.googleapis.com/tekton-releases/pipeline/latest/release.yaml

.PHONY: install-task-git-clone
install-git-clone:
	kubectl apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/git-clone/0.6/git-clone.yaml

.PHONY: install-task-kaniko
install-task-kaniko:  
	kubectl apply -f https://raw.githubusercontent.com/tektoncd/catalog/main/task/kaniko/0.6/kaniko.yaml