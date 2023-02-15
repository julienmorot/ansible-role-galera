# Introduction

Ansible module to deploy a galera cluster

# Usage

```yaml
---
- hosts: db
  become: yes
  remote_user: julien
  vars:
    galera_cluster_nodes:
      - db01
      - db02
      - db03
    galera_bootstrap_node: db01
    galera_bootstrap_cluster: true
  roles:
      - ansible-role-galera
```

Mandatory variables :

- galera_cluster_nodes
- galera_bootstrap_node
- galera_bootstrap_cluster true to init cluster, defaults false

# Run playbook

- default : deploy configuration
- with var galera_bootstrap_cluster set to true init cluster
- with --tags galera_stop : properly shutdown all nodes with galera_bootstrap_node as last node
- with --tags galera_start : first start galera_bootstrap_node then other cluster members
