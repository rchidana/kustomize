# kustomize
kustomize Examples

### First clone this GitHub Repository onto your local machine
```
git clone https://github.com/rchidana/kustomize
cd kustomize

# Check if kubectl supports kustomize
kubectl kustomize

# You will get an error - error: unable to find one of 'kustomization.yaml', 'kustomization.yml' or 'Kustomization'
# Kustomize needs to be run against a folder that has kustomization.yaml

# To check out the manifests in base folder - FYI, base manifests are usually not used as such
kubectl kustomize base

# Checkout the manifests of dev environment & verify if the overlays are applied correctly
kubectl kustomize overlays/dev/

# To deploy/apply dev manifests
kubectl apply -k overlays/dev/
# Verify the deployment, po and svc
kubectl describe deploy web-deployment
kubectl describe po
kubectl describe svc

```

# Task!!

Modify this code to ensure that the deployments happen to specific namespaces: <br>
overlays/dev --> Should get deployed to 'dev-ns' namespace <br>
overlays/prod --> Should get deployed to 'prod-ns' namespace <br>


