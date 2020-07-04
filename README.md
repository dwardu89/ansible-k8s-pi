# Ansible Playbook for K8s on a Raspberry Pi 4 Cluster

This repository holds the ansible playbook and roles created to spin up a Kubernetes cluster on a set of Raspberry Pi 4 8GB models.
You can use it on less powerful models that have at least 2 cores.

## Setup

This setup assumes that you've flashed a copy of _Ubuntu 20.04 LTS 64-bit_, enabled ssh by adding an empty `ssh` file in the `/boot` folder to it and made it acquire a fixed IP address. You should set a static IP address to each PI so you can ensure you are always going to ssh into the same PI when ever you run the ansible playbook.

You need to have an SSH public/private key pair created created at `~/.ssh/id_rsa.pub` and `~/.ssh/id_rsa` respectively.

When you've set up a stateic IP address, update the IP addresses in the `inventory` file for the `master` and `workers` and also update the `ansible_password` which is the password required to ssh into the raspberry pi. This will only be used to establish a connection for the first time, and once you have ran the playbook once, you will be able to ssh in using your private key located at `~/.ssh/id_rsa`.

## Running the playbook

Run `ansible-playbook main.yml` and watch the progress.
You will end up with a kubernetes cluster set up, ssh into the `master` node and run `kubectl get nodes` to see the nodes that are in the cluster.
You can copy the `kubeconfig` from the master found at `~/.kube/config` and append it to your existing kubeconfig so you can work with the cluster on your device without the need to ssh.

