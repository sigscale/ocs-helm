# Manage Google Kubernetes Engine (GKE)

## Create a GKE Autopilot Cluster
	gcloud container clusters create-auto ocs-cluster \
			--project sigscale-ocs --location=asia-east1b

## Configure `kubectl` to use the GKE Cluster
	gcloud container clusters get-credentials ocs-cluster

# Get the Pods (after `helm install`)
	$ kubectl get pods
	NAME                   READY   STATUS    RESTARTS   AGE
	ocs-1-sigscale-ocs-0   1/1     Running   0          29s

## Get the log of init container
	kubectl logs ocs-1-sigscale-ocs-0 -c ocs-init

## Get the log of container
	kubectl logs ocs-1-sigscale-ocs-0

## Describe the pod
	$ kubectl describe pod ocs-1-sigscale-ocs-0

## Attach to a GKE pod deployment which runs ocs container
	$ kubectl attach -ti ocs-1-sigscale-ocs-0 -c ocs -i -t
	(ocs@ocs-1-sigscale-ocs-0.otp-ocs.default.svc.cluster.local)5>
### There is no `detach` so you'll need to kill the `kubectl attach` process

