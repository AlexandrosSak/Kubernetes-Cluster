# Kubernetes-Cluster
Creating a Kubernetes cluster using Kubespray
In this example I created 4 vms : 

1.Kubernetes Master Node (control plane) , OS-Rocky linux 9
2.Kubernetes worker1                     , OS-Rocky linux 9   
3.Kubernetes worker2                     , OS-Rocky linux 9
4.Ansible host controller                , OS-Ubuntu 22.04.2 LTS  (I utilize this vm to run the kubespray and do the kubernetes cluster installation)



All vms were created with Oracle VM Virtual Box with a NAT Network making the appropriate port forwardings.
