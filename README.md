# INSTALL ISTIO
https://github.com/istio/istio/releases/download/1.9.0/istio-1.9.0-win.zip

Add istio/bin folder to your PATH environment variable, on Windows

### Check if istioctl is installed
```bash
istioctl version
```

### Install istio
```bash
istioctl install --set profile=demo -y
```

### Check namespaces created
```bash
kubectl get ns
```

### Get istio pods
```bash
kubectl get pods -n istio-system
```

### Para que istio inyecte esos sidecard en todos los pods de un namespace
```bash
kubectl label namespace default istio-injection=enabled
```

### Aplicamos algún manifiesto kubernetes
```bash
kubectl apply -f example-app.yaml
```

### Descibimos el pod
```bash
kubectl describe pod example-app-6f9f9b7b7f-4q9qj
```

Podemos ver que en el pod se ha añadido un sidecar de istio (istio-proxy)


# Kiali (Dashboard)
Kiali es un dashboard que nos permite visualizar la topología de nuestra aplicación, así como las llamadas entre los distintos servicios.
```bash
istioctl dashboard kiali
```

