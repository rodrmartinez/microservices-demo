
.PHONY: kind-create
kind-create:
	kind create cluster --name=cre-labs-flux

.PHONY: kind-delete
kind-delete:
	kind delete cluster --name=cre-labs-flux

.PHONY: config-github
config-github:
 export GITHUB_TOKEN=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	&\
 export GITHUB_USER=rodrmartinez

.PHONY: install-flux
install-flux: 
	flux bootstrap github \
  --owner=$GITHUB_USER \
  --repository=fleet-infra \
  --branch=main \
  --path=./clusters/my-cluster \
  --personal

.PHONY: get-admin-password
get-admin-password:
	kubectl -n argocd get secret argocd-
	ainitial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo

	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

