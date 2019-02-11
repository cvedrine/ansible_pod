## Roles Ansible pour déployer et mettre à jour POD v2 sur 1 ou plusieurs serveurs

### Créer son inventaire à partir de inventories/template.yml

### Lancer une install :

ansible-playbook --inventory ./inventories/test.yml --ask-pass --ask-become-pass  pod_install.yml

### Lancer une update :

ansible-playbook --inventory ./inventories/test.yml --ask-pass --ask-become-pass  pod_update.yml
