Download and install Isstio

```bash
curl -L https://istio.io/downloadIstio | sh -
cd istio-*
export PATH=$PWD/bin:$PATH
```

Install demo components

```bash
istioctl install --set profile=demo -y
```

Enable istio-injection

```bash
kubectl label namespace default istio-injection=enabled
```


Check

```bash
kubectl get crd | grep istio
```
