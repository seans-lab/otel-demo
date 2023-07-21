
# otel-demo

Create the namespace app for the Otel Demonstration App and set the context for Kubernetes to use the app namespace.
```
kubectl create namespace app 
kubectl config set-context --current --namespace=app
```
Add the helm repo for the Otel Demonstration App, Install the App using the Helm Repo and check that the pods have loaded correctly.
```
helm repo add open-telemetry https://open-telemetry.github.io/opentelemetry-helm-charts
helm install my-otel-demo open-telemetry/opentelemetry-demo
kubectl get pods
```

Create the namespace nginx-ingress for the NGINX Ingress Controller.
```
kubectl create namespace nginx-ingress
kubectl config set-context --current --namespace=nginx-ingress
```

Add the NGINX ingress Controller Helm repo for the NGINX Ingress Controller and install the NGINX Ingress Controller. Check that the ingress controller has been installed.

```
helm install my-release oci://ghcr.io/nginxinc/charts/nginx-ingress --version 0.18.0
kubectl get svc

```
