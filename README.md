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
