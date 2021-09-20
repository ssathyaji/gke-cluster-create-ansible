## GKE Cluster deployment Ansible files

Ansible play-book for deploy private k8s cluster in GCP

This is bases on the ansible 2.9 and gcloud commands.
Ansible Documentation for Cluster create and Node pool create.

https://docs.ansible.com/ansible/2.9/modules/gcp_container_cluster_module.html

https://docs.ansible.com/ansible/2.9/modules/gcp_container_node_pool_module.html

## Getting Started

The followig mantadory environment variables in env-file need to be set before calling ansible-playbook

 * `GKENAME`: Name of the Kubernetes cluster
 * `NODE_COUNT`: how many nodes should we provision, defaults to 4
 * `USERNAME`: Cluster api access username
 * `PASSWORD`: Cluster api access password
 * `FLAVOR_ID`: Allows to configure the exact node type
 * `DISK_SIZE`: Cluster nodes disk capcity, defaults to 40GB
 * `ZONE`: The zone is which your cluster is located
 * `NODE_LOCATION`: Specify the zones in which this cluster's nodes run.
 * `PROJECT`: GCP Project ID
 * `AUTH_KIND`: Authentication method, defaults serviceaccount
 * `SERVICE_ACCOUNT_FILE`: Service Acclount file location path
 * `NODE_POOL_NAME`: Cluster node pool name
 * `NP_INITIAL_NODE_COUNT`: Initial Node clount per pool
 * `ENABLE_PRIVATE_CLUSTER`: Install Private cluster, without expose to internate, Defaults value is enable
 * `SUBNET_NAME`: Private cluster node network
 * `DISK_TYPE`: Nodes disk type pd-standard or pd-ssd, defauls is pd-standard
 * `MAX_NODE_NODEPOOL`: Node pool autoscale max nodes per pool
 * `MIN_NODE_NODEPOOL`: Node pool minimum number of nodes
 * `K8S_NETWORK_NAME`: name of the GKE network
 * `K8S_CLUSTER_SUBNET_NAME`: name of the subnet in GKE network

## Install Cluster
```$ source env-file``` 

```$ ansible-playboot site.yml```

## Delete Cluster
```$ source env-file```

```$ ansible-playbook destroy.yml```
