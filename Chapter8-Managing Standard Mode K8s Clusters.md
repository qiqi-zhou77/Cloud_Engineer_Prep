# Viewing the status of a K8s Cluster
## In cloud console
## Pinning service to top of navigating bar
    - Persistent volumnes are durabel disks that are managed by K8s and implemented using Compute Engine
    persisten disks
    - A storage class is a type of storage with a set of policies specifying quality of service, backup policy and a provisitoner
    - Pending: pods are downloading images; Succeeded: pods determinated successfully; Faled: at least one container failed; Unkown: control plane cannot reach the node and stauts cannot be determined

## Using SDK and Shell
    - ensure that you have a properly configured kubeconfig file, which contain infromation on how to communicate with the cluster API

# Adding, Modifying, and Removing Nodes
## With Cloud Console
## With SDK and Shell


#  Adding, Modifying and Removing Pods

**it is considered best practice not to manipulte pods directly. Kubernetes will maintain the number of pods specified for a deployment, if zou would like to change of the number of pods, you need to change the deployment configuration**

## With Cloud Console
- Pods are managed thru deployment -- replica, which is the number of pods running the application specified in the deployment
- Resizing in Action

## With SDK and Shell

# Adding, Modifying and Removing Services

**Service is a way to expose an application on a set of pods to other application and users on a network**
**The term services, is more a sysnonym of applications**



## With Cloud Console
- Thru deployment

## With SDK and Shell



# Creating Repo in the artifact registry
- Artifact Registry is used for storing container images
- Registry of lots of types including Docker, Maven, Pyhthon....
-  K8s Engine makes use of container images stored in a focker repository

## Viewing Image Repo and Image Details with Cloud Console
