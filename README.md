# Odoo 11 Installation Guide on Linux

This guide provides instructions for installing Odoo 11 on a Linux system using Python 3.7. It includes steps for setting up the Python environment and Odoo itself.

## Prerequisites

Ensure your system is updated and install the required packages:


    sudo apt update
    sudo apt install -y make build-essential libssl-dev zlib1g-dev \
    libbz2-dev libreadline-dev libsqlite3-dev wget curl llvm \
    libncurses5-dev libncursesw5-dev xz-utils tk-dev libffi-dev \
    liblzma-dev python-openssl

### Python 3.7 Setup
1. Install `pyenv` (if not already installed)
If `pyenv` is not installed, you can install it using the following command:
    
    curl https://pyenv.run | bash

2. Configure pyenv
Add the following lines to your `~/.bashrc` or `~/.zshrc` to set up pyenv:

    export PATH="$HOME/.pyenv/bin:$PATH"
    eval "$(pyenv init -)"
    eval "$(pyenv virtualenv-init -)"

Reload your shell configuration:

    exec "$SHELL" # Or just restart your terminal

3. Install Python 3.7
Use pyenv to install Python 3.7:

    pyenv install 3.7

4. Create a Virtual Environment
Create a virtual environment using the installed Python version:

    virtualenv -p $(pyenv which python3.7) .venv
Alternatively, you can use:

    /home/$USER/.pyenv/shims/python3.7 -m virtualenv .venv

## Odoo 11 Installation
1. Clone the Odoo Repository
Clone the Odoo 11 repository from GitHub:

    git clone https://www.github.com/odoo/odoo --depth 1 --branch 11.0 --single-branch odoo11

2. Install OpenSSL
Install OpenSSL if it is not already installed:

    sudo apt install openssl@1.1

Download and Move the OpenSSL configuration [file]():

    sudo mv ~/Downloads/openssl.cnf /etc/ssl/

3. Install Python Dependencies
Navigate to the Odoo 11 directory and install the required Python packages:

    pip install -r requirements.txt



