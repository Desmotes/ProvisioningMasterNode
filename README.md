# Provisioning

Desmotes project uses [Ansible automation tool](https://www.ansible.com/).

This git project constitutes the provisioning repository of the master node. Provisioning project installs the appropriate software to the master node.

More specifically, this project installs the following parts.

* Desmotes User / Group
* Build essential
* Angular

# Installation 
 
## Local provisioning

> ansible-playbook --limit="all" --inventory-file=ProvisioningMasterNode/master_local -v --vault-password-file=ProvisioningMasterNode/.vault_pass ProvisioningMasterNode/master_node.yml
