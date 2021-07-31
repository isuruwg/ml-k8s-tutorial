# TOC <!-- omit in toc -->

- [1. Introduction](#1-introduction)
  - [1.1. Generating the images](#11-generating-the-images)
- [2. Kubernetes introduction](#2-kubernetes-introduction)
  - [2.1. Installing for local development](#21-installing-for-local-development)
    - [2.1.1. Install Kubectl](#211-install-kubectl)
    - [2.1.2. Install KIND](#212-install-kind)

# 1. Introduction

This repo contains my notes for the course [Docker and Kubernetes: The complete guide](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide)

## 1.1. Generating the images

The course provides xml files for draw.io drawings. Open them in draw.io and do, File -> Export as -> PNG and specify 20 for border.

# 2. Kubernetes introduction

![image](images/diagrams-05%20-%20kube.png)

**What is Kubernetes?** System for running many different containers over multiple different machines

**Why use Kubernetes?** When you need to run many different containers with different images

![image](images/diagrams-09%20-%20dev.png)

![image](images/diagrams-08%20-%20arch.png)

## 2.1. Installing for local development

There are [multiple ways](https://brennerm.github.io/posts/minikube-vs-kind-vs-k3s.html) to install Kuberenetes locally for development. Here, I'll use [KIND](https://kind.sigs.k8s.io/docs/user/quick-start/). 

### 2.1.1. Install Kubectl

Follow [Install using native package management](https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/#install-using-native-package-management). Note: As of 2021-05-06, the native package management method installs the latest stable kubectl version.


### 2.1.2. Install KIND

[REF](https://kind.sigs.k8s.io/docs/user/quick-start/)

```bash
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
chmod +x ./kind
mkdir -p ~/KIND/kind_0_11_1/
mv ./kind ~/KIND/kind_0_11_1/
```

Add the following to the `~/.bashrc` (on Ubuntu) to add KIND to your path.

```bash
export PATH="~/KIND/kind_0_11_1:$PATH"
```
Create cluster (The default cluster is named kind): 

```bash
kind create cluster
```

If you want to delete a cluster use `kind delete cluster` command.


