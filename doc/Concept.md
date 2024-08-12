# Comparative analysis of local Kubernetes deployment tools

## Introduction
This paper presents a comparative analysis of Kubernetes-based tools for deploying and testing clusters in a local environment: minikube, kind, and k3d.

## *Comparison of characteristics*

| characteristics  | minikube | kind  | k3d |
|:----------------- |:----------|:-------|:-----|
| OS | Linux, Windows, MacOs|Linux, Windows, MacOs| Linux,  MacOs |
| runtime | VM | container | native |
| supported architectures| AMD64 | AMD64 | AMD64, ARMv7, ARM64|
| supported container runtimes | Docker,CRI-O,containerd,gvisor | Docker | Docker, containerd |
| memory requirements |	2GB | 8GB (Windows, MacOS) | 512 MB |
| requires root? | no | no | yes (rootless is experimental) |
| multi-cluster support | yes | yes | no (can be achieved using containers) |
| multi-node support |no | yes | yes |
 project page | [minikube](https://minikube.sigs.k8s.io/docs/) | [kind](https://kind.sigs.k8s.io/) | [k3s](https://k3d.io/v5.7.3/) |

## Advantages and Disadvantage

| Tool  | Advantages | Disadvantage | 
|-------|------------|---------------|
| minikube |- Easy to install and use.<br> - Supports many additional features such as cluster status visualization, monitoring and management.|- May be slow for larger clusters.<br> - Can be resource-intensive.<br> - Requires manual configuration for some features.|
| kind |- Fast and easy to use.<br> - Provides good isolation between clusters. |- Limited support for additional features and integrations.<br> -  Possible performance issues when using larger clusters.|
| k3d  |- Lightweight and fast.<br> -  Provides a convenient way to create and manage many clusters.| - Possible stability problems when working with more complex configurations.<br> -  Limited support for additional features and integrations.|

## Conclusions

Taking into account the characteristics, advantages and disadvantages of each tool, the following conclusions and recommendations can be made:

 - Minikube is suitable for quickly launching and testing applications in Kubernetes on a local computer. This is a good option for beginners or for a quick PoC deployment.
  - Kind is an easy-to-use and fast tool for creating local Kubernetes clusters using Docker. It can be useful for testing and development.
  - K3d allows you to quickly create and manage many local Kubernetes clusters. It can be an option for more complex scenarios where you need to manage multiple clusters at the same time.

So, if you're looking for a lightweight, fast, and easy-to-use tool for local development and testing, K3d might be a great fit for your project.

### Reminder
Using Docker involves licensing risks for commercial use. Podman is a license-free alternative to Docker that can be used with all of the tools discussed.