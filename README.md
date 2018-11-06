 # Demo of Azure function runtime on knative

This is a demo ... to test stuff

Prep your function

```
func init
func new -t "Queue trigger" --name foo
```

Edit your queue name in `foo/function.json`

Store your Azure Storage connetion string in a k8s secret

Make sure that the Azure buildtemplate is created

```
kubectl apply -f knative-build-template.yaml
```

Deploy your function via a knative configuration

```
kubectl apply -f function.yaml
```

What the build happen, revision get ready, deployment created and pod started

then send message via Azure Storage queue portal interface

check the logs on your Pod.
