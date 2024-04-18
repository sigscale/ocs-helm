# Manage Google Kubernetes Engine (GKE)

## Create a GKE Autopilot Cluster
	gcloud container clusters create-auto ocs-cluster

## Configure `kubectl` to use the GKE Cluster
	gcloud container clusters get-credentials ocs-cluster

## Get the Pods (after `helm install`)
	kubectl get pods

## Get the log of init container
	kubectl logs ocs-1-sigscale-ocs-0 -c ocs-init

## Get the log of container
	kubectl logs ocs-1-sigscale-ocs-0

## Describe the pod
	kubectl describe pod ocs-1-sigscale-ocs-0

## Attach to a GKE pod deployment which runs ocs container
	$ kubectl attach -ti ocs-1-sigscale-ocs-0 -c ocs -i -t
	(ocs@ocs-1-sigscale-ocs-0.otp-ocs.default.svc.cluster.local)1>
### There is no `detach` so you'll need to kill the `kubectl attach` process

