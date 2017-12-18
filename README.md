## Setting up haproxy via Ansible

This project presents an Ansible playbook to setup external loadbalancer for our HA Kubernetes cluster. The front end here would redirect requests to the replicated masters of our K8S cluster.

### Inventory

The inventory contains the details of backend servers and other sensitive information e.g. proxy details. The same sensitive data is stored in a vault file that need to be updated prior to playbook execution using the following command

```
$ ansible-vault edit inventory/group_vars/loadbalancers/vault.yml
```

### Playbook execution

```
$ ansible-playbook -i inventory/hosts -kK -v --ask-vault-password playbook.yml
```
