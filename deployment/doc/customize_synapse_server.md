# Customize synapse server

## Inventory

Open `sample_inventory.ini` and replace [custom_ip or fqdn] with the one from your VM. 

```sh
# rename inventory.ini
mv sample_inventory.ini inventory.ini
```

## Synapse config

Open `vars/sample_synapse_vars.yaml` and replace all [...] fields with your custom configuration. Check comment line for description.

```sh
# rename synapse_vars.yaml
mv sample_synapse_vars.yaml synapse_vars.yaml
```