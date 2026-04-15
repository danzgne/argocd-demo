# An Example Application for ArgoCD Demo

This is a simple example repository for testing ArgoCD, a GitOps tool for Kubernetes.

## Getting Started

**1. Ensure you have a Kubernetes cluster ready.**

**2. Install ArgoCD into the Kubernetes cluster:**
```bash
kubectl create namespace argocd  
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

*If you want to review the `install.yaml` in detail, you can download, read, and apply the manifest manually.*

**Note:** The following steps apply to **Minikube or local Kubernetes clusters**. If using a different deployment environment, please refer to your platform's documentation for accessing the ArgoCD service.

**3. Access ArgoCD UI:**
```bash
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd
```

**4. Log in to the ArgoCD UI:**

The default username is ***admin***.  
You can retrieve the initial admin password by running:
```bash
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo
```

## Links
* Config repo: [https://gitlab.com/nanuchi/argocd-app-config](https://gitlab.com/nanuchi/argocd-app-config)

* Docker repo: [https://hub.docker.com/repository/docker/nanajanashia/argocd-app](https://hub.docker.com/repository/docker/nanajanashia/argocd-app)

* Install ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd](https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd)

* Log in to ArgoCD: [https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli](https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli)

* ArgoCD Configuration: [https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/](https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/)

## References

- Credits to **TechWorld with Nana** channel for the demo manifests:  
    - GitLab Repository: https://gitlab.com/nanuchi/argocd-app-config/  
    - Youtube Video: https://www.youtube.com/watch?v=MeU5_k9ssrs