# ocs-helm
Helm chart for deploying SigScale OCS on Kubernetes

# Deploy a SigScale OCS StatefulSet
	$ helm install ocs-1 sigscale-ocs
	NAME: ocs-1
	LAST DEPLOYED: Sat Mar 16 20:50:36 2024
	NAMESPACE: default
	STATUS: deployed
	REVISION: 1
	TEST SUITE: None
	NOTES:
	Installed sigscale-ocs instance as release name: ocs-1

# List Helm releases
	$ helm list
	NAME 	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART             	APP VERSION
	ocs-1	default  	1       	2024-03-16 20:59:45.376028 +0800 PST	deployed	sigscale-ocs-0.1.0	3.3.15-3

# Remove a SigScale OCS StatefulSet
	$ helm uninstall ocs-1
	release "ocs-1" uninstalled

