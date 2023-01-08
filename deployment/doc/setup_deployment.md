# Setup deployment server

## Requirements

- VM with Linux (Tested with Ubuntu 22.10)
- SSH key
- Python3 with Virtual Environment (venv)

## Install ansible in virtual environment

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