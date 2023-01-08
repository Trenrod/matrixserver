
# Customize deployment

## Add ssh key to access matrix server via ansible

```sh
# Make sure you are in the deployment directory
# pwd
# {Project}/deployment

# Copy private pem
cp {Filepath to your private pem} ./keys/matrix_key.pem
```

## Configure ansible

For ansible to be able to access the VM. `inventory.ini` has to be correctly configured.

### Copy sample inventory.ini to customize it

```sh
# Copy rename sample and to customize
cp sample_inventory.ini inventory.ini
```

Open `inventory.ini` with an editor and customize entries if needed.

### Test connection

```sh
ansible matrixserver -m ping -i inventory.ini
```

Fix any errors before proceed.
