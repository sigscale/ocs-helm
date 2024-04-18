# ocs-helm
Helm chart for deploying SigScale OCS on Kubernetes

## Deploy a SigScale OCS StatefulSet
	helm install ocs-1 sigscale-ocs

## List Helm releases
	helm list

## Remove a SigScale OCS StatefulSet
	helm uninstall ocs-1

## Deploy with localization overides in `sys.config`
	helm install \
			--set ocsConfig.create=true \
			--set-file ocsConfig.sysConfig=sys.config \
			ocs-1 sigscale-ocs

