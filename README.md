# Provisioning

Desmotes project uses [Ansible automation tool](https://www.ansible.com/).

This git project constitutes the provisioning repository of the master node. Provisioning project installs the appropriate software to the master node.

More specifically, this project installs the following parts.

* Desmotes User / Group
* Build essential
* Ruby
* NodeJS

# Installation 
 
## Local provisioning

Initially, you have to create a .vault_pass file with the password (plain text) in the Provisioning root folder

> echo "text" >  .vault_pass 

After that you have to create the pass.yml file using vault mechanism. Don't forget to pass in the creation of the folder the same password like .vault_pass file.

> ansible-vault create vars/pass.yml


> ---

> desmotes_password: <password> 

Secondly, you have to copy your rsa keys for desmotes user.

> mkdrir -p ProvisioningMasterNode/keys

> cp <id_rsa.pub> ProvisioningMasterNode/keys/

Finally, run the following command

> ansible-playbook --limit="all" --inventory-file=ProvisioningMasterNode/master_local -v --vault-password-file=ProvisioningMasterNode/.vault_pass ProvisioningMasterNode/master_node.yml
