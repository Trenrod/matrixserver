# Provisioning Matrix server with Ansible



## [Setup deployment server](doc/setup_deployment.md)

## [Setup connection to matrix vm](doc/setup_connection_to_matrix_vm.md)

## [Customize synapse server](doc/customize_synapse_server.md)

## Execute deployment

After all above has been applied

```sh
# Switch to ansible virtual environment
source .venv/bin/activate

# Execute deployment
ansible-playbook -i inventory.ini playbook_matrix.yaml
```