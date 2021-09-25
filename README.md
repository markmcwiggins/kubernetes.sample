# kubernetes.sample
Sample Kubernetes YAML files for use with GCP
=============================================

You first need to bring up a cluster. On GCP you can do that with the cloud console, or with a script with a bunch of parameters. On stock Kubernetes there is a shell script called **kube-up.sh** that you can run that brings up a cluster that you can deploy against.

Then you can deploy these 4 files:

```
kubectl apply -f deploy.yaml
kubectl apply -f servic443.yaml
kubectl apply -f ssl-cert.yaml   # this one will only work with GKE clusters
kubectl apply -f ingress.yaml
```

Then wait 5 minutes and try:

kubectl get ing -A

and if that looks OK (with an IP address), you can give

kubectl describe ing -A

and it should show status HEALTHY ... eventually!

Good luck!






