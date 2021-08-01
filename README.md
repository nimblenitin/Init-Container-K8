# Init-Container-K8

Init containers in on a Pod allows to create preparatory checks before running other containers in a Pod. Standard example is you want a web application to be available only if the database connected to it is up and running. If not Init container can prohibit the application container to be served.

Simple example to to demonstrate Init container.

Steps followed:

*As Root*
```

1. Create the YAML file and apply it to deploy an Nginx image which has a init container which writes random number into a persistent volume.
$ kubectl apply -f pod_initcontainer.yaml

2. Describe the pod to find the IP address
$ kubectl describe pod pod_initcontainer.yaml

3. Ping the IP address to see the data written into persistent volume by the Init container.
$ ping <IP address>

```
*As Root*

