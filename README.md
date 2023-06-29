# Kubernetes-Cluster
Creating a Kubernetes cluster using Kubespray
In this example I created 4 vms : 

1.Kubernetes Master Node (control plane) , OS-Rocky linux 9

2.Kubernetes worker1                     , OS-Rocky linux 9  
 
3.Kubernetes worker2                     , OS-Rocky linux 9

4.Ansible host controller                , OS-Ubuntu 22.04.2 LTS  (I utilize this vm to run the kubespray and do the kubernetes cluster installation)



All vms were created with Oracle VM Virtual Box with a NAT Network making the appropriate port forwardings.


Prerequisites
To follow along, you need this:

3 VMs with a compatible OS
Regarding hardware resources, controller nodes need at least 1.5 GB RAM, worker nodes 1GB of RAM
SSH access to these serversPrerequisites


Part I - Creation of VMs and Network

Part II - Configure Kubespray

Kubespray Controller Setup
The Kubespray controller is a machine on which you will install the Kubespray environment and from which you will have access to all the servers which are going to be a part of your cluster. Preferably, this controller is not also part of your cluster.

On this controller, following the official documentation, we will clone the Kubespray repo and install ansible first in a Python virtual environment - a separated workspace, similar to a container, that encapsulates all required software versions into one.
Run the commands indicated in Configure Kubespray.

Part III - Creating the Inventory

First, copy the sample inventory definitions from the repo
cp -rfp inventory/sample inventory/mycluster

then bootstrap the inventory file details by running a command that lists all the IPs of your server (from controller to workers)

Part IV - Run the ansible playbook and inventory for kubespray to start the cluster instalation. In my case the command is : ansible-playbook -i /root/kubespray/kubespray/inventory/sample/inventory.ini ~/kubespray/kubespray/playbooks/cluster.yml -Kb

