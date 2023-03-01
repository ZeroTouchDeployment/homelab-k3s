# Homelab - K3S

[![Continuous Integration](https://github.com/zerotouchdeployment/homelab-k3s/workflows/Continuous%20Integration/badge.svg)](https://github.com/zerotouchdeployment/homelab-k3s/actions?query=workflow%3A%22Continuous+Integration%22)
[![Continuous Deployment](https://github.com/zerotouchdeployment/homelab-k3s/workflows/Continuous%20Deployment/badge.svg)](https://github.com/zerotouchdeployment/homelab-k3s/actions?query=workflow%3A%22Continuous+Deployment%22)
[![Go Report Card](https://goreportcard.com/badge/github.com/zerotouchdeployment/homelab-k3s)](https://goreportcard.com/report/github.com/zerotouchdeployment/homelab-k3s)
[![Coverage Status](https://codecov.io/github/zerotouchdeployment/homelab-k3s/coverage.svg?branch=master)](https://codecov.io/github/zerotouchdeployment/homelab-k3s?branch=master)
[![GitHub release](https://img.shields.io/github/release/zerotouchdeployment/homelab-k3s.svg)](https://github.com/zerotouchdeployment/homelab-k3s/releases/latest)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://github.com/zerotouchdeployment/homelab-k3s/blob/master/LICENSE)

## Introduction

Ansible playbook to deploy and configure an HA Kubernetes cluster with k3s, kube-vip, metallb, traefik and more.

The goal is a fully automated build of an HA Kubernetes cluster ready for your homelab.

It uses the following core components:
- [kube-vip](https://kube-vip.io/) - Load balancer for the Kubernetes control plane nodes.
- [metallb](https://metallb.universe.tf/) - Load balancer for Kubernetes services.
- [cert-manager](https://cert-manager.io/) - Operator to request SSL certificates and store them as Kubernetes resources.
- [calico](https://www.tigera.io/project-calico/) - Container networking interface for inter pod and service networking
- [external-dns](https://github.com/kubernetes-sigs/external-dns) - Operator to publish DNS records to Cloudflare (and other providers) based on Kubernetes ingresses



## System requirements
- For the K3S cluster, use at least three (virtual) machines with x64 or arm64 processor architecture running Debian, Ubuntu or Rocky Linux.
- Machines should have passwordless SSH access. To configure this, see below.
- Make sure Ansible version 2.11+ is installed on your control node, the machine you are running the ansible commands. 
- Install required Ansible Galaxy collections this playbook uses by running `sh requirements.sh` on the control node.
- The [`netaddr package`](https://pypi.org/project/netaddr/) must be available to Ansible. 



## Getting started


### Requirements


### Install
Start provisioning the cluster with:
```bash
ansible-playbook install.yaml -i inventory/<folder>/hosts.ini
```

### Test
Be sure you can reach the VIP defined in inventory/sample/group_vars/all.yaml as apiserver_endpoint


Get nodes




## Uninstall
To uninstall k3s homelab:
```bash
ansible-playbook uninstall.yaml -i /inventory/hl/hosts.ini
```



Prerequisites:
Development machine needs following packages:
- ansible-core, tar, python3-netaddr




## Configure passwordless SSH access
- Create authentication SSH-Keygen keys on the control node with `ssh-keygen -t rsa`
- Upload key to worker nodes with `ssh-copy-id <user@ip-address of node>`

## Install Ansible


## Install netaddr package



## Thank you


