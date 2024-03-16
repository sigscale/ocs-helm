# Manage Google Kubernetes Engine (GKE)

## Create a (tiny) GKE Cluster
	$ gcloud container clusters create cluster-1 \
			--machine-type e2-small \
			--disk-size 10 \
			--num-nodes 3

## Configure `kubectl` to use the GKE Cluster
	$ gcloud container clusters get-credentials cluster-1
	Fetching cluster endpoint and auth data.
	kubeconfig entry generated for cluster-1.

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

