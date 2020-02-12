## Roles Ansible pour déployer et mettre à jour POD v2 sur 1 ou plusieurs serveurs
basé sur https://github.com/Furiouss38/pod_install
https://github.com/geerlingguy/ansible-role-rabbitmq
geerlingguy.elasticsearch
et geerlingguy.postgresql



### Créer son inventaire à partir de inventories/template.yml
test.yml, prod.yml etc

### Généation des vault
ansible-vault encrypt_string --vault-password-file ~/ansible/.vault_podv2.txt '*****' --name 'bind_pwd'

### Lancer une install :

ansible-playbook --inventory ./inventories/test.yml --tags "bdd,rabbitmq,elasticsearch,pod,first_install,libencode,nginx" --vault-password-file ~/ansible/.vault_podv2.txt pod_install.yml

Le superuser ainsi que l'index elasticsearch sont à creer manuellement (voir documentation podv2)

### Lancer une update :

ansible-playbook --inventory ./inventories/test.yml  --vault-password-file ~/ansible/.vault_podv2.txt  pod_update.yml
