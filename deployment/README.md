# Provisioning Matrix server with Ansible

## Setup existing VMS

### Requirements

- VM with Linux (Tested with Ubuntu 22.10)
- SSH key
- Python3 with Virtual Environment (venv)

### Install ansible in virtual environment

```sh
# Make sure you are in the deployment directory
# pwd
# {Project}/deployment

# Install virtual environment locally
python3 -m venv .venv

# Enter virtual environment
source .venv/bin/activate

# Install all required libs
pip install -r requirements.txt
```

## Customize deployment

### Add ssh key to access matrix server via ansible

```sh
# Make sure you are in the deployment directory
# pwd
# {Project}/deployment

# Copy private pem
cp {Filepath to your private pem} ./keys/matrix_key.pem
```

### Configure ansible

For ansible to be able to access the VM. `inventory.ini` has to be correctly configured.

#### Copy sample inventory.ini to customize it

```sh
# Copy rename sample and to customize
cp sample_inventory.ini inventory.ini
```

Open `inventory.ini` with an editor and customize entries if needed.

#### Test connection

```sh
ansible matrixserver -m ping -i inventory.ini
```

Fix any errors before proceed.

##### Apply deployment

```sh
ansible-playbook -i inventory.ini playbook_matrix.yaml
```

#### TODO

#### Deployments

- [X] Install docker
- [ ] Decide for email Service provider (e.g. SMS-AWS)
- [ ] Create docker service for
  - [ ] Cretae docker service network diagram
  - [ ] Caddy2
  - [ ] Matrix
  - [ ] Postgres
  - [ ] Network

#### Development

- [ ] Decide CI/CD pipeline (e.g. Github actions)
