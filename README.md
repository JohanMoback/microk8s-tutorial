# microk8s-tutorial

## Install MicroK8s

1. Download the MicroK8s installer
    
    **brew install ubuntu/microk8s/microk8s**
2. Run the installer
    
    **microk8s install**
3. Check the status while Kubernetes starts
    
    microk8s status --wait-ready
4. Turn on the services you want
    
    **microk8s enable dashboard**
    
    **microk8s enable dns**
    
    **microk8s enable registry**
    
    **microk8s enable istio**
5. Start using Kubernetes!
    
    **microk8s kubectl get all --all-namespaces**
6. Access the Kubernetes dashboard
    
    **microk8s dashboard-proxy**

## Enable/Disable MicroK8s
 - **microk8s start**

    Access the K8s dashboard

    **micork8s dashboard-proxy**

 - **microk8s stop**

*Make sure that you open a new terminal window before running a new microk8s session*

# Using HELM with MicroK8s

1. Install HELM
Follow the Helm installation instructions for your operating system. You can find the latest instructions on the official Helm website: [https://helm.sh/docs/intro/install/](HELM Install)

2. Initialize Helm on MicroK8s
After installing Helm, you need to initialize it and configure it to work with MicroK8s:

**microk8s.enable dns**

**helm init --wait**

# Deploy HELM charts to your MicroK8s cluster
1. Add ArtifactHub as a Helm Repository:

    **helm repo add artifacthub https://artifacthub.github.io/hub**

You can also add other HELM repositories sush as:

**helm repo add bitnami https://charts.bitnami.com/bitnami**


2. Update Helm Repositories:

    **helm repo update**

3. Search for the NGINX Chart:

    **helm search repo artifacthub/nginx**

4. Install the NGINX Chart:

**helm install my-nginx artifacthub/nginx** 

You can also install via bitnami: 

**helm install my-nginx bitnami/nginx**


If you want a specific version.

**helm install my-nginx artifacthub/nginx --version X.X.X**


