# Ansible Collection - gohitech.core

Documentation for the collection.

## Deploy using git clone

The Collection is using Git Submodules to pool a collection of roles.
IT does nto appear that the `ansible-galaxy collections` git pull command will work with submodules.
The following steps will allow the operation to function as expected.

```bash
# Make the collection parent namespace directory
# This is the default location so change this path if you have modified your Ansible config.
mkdir -p ~/.ansible/collections/ansible-collections/gohitech

# Git clone the repository and the submodules
git clone --recursive https://github.com/GoHiTech/gohitech.core.git ~/.ansible/collections/ansible-collections/gohitech/core

# Update Git Submodule references to the HTTPS equivalent
cd ~/.ansible/collections/ansible-collections/gohitech/core
git submodule set-url -- roles/docker https://github.com/dean-taylor/ansible-role-docker.git
git submodule set-url -- roles/glusterfs https://github.com/dean-taylor/ansible-role-glusterfs.git
git submodule set-url -- roles/microk8s https://github.com/dean-taylor/ansible-role-microk8s.git
git submodule update --init --recursive
```

With SSH keys

```bash
mkdir -p ~/.ansible/collections/ansible-collections/gohitech
git clone --recursive https://github.com/GoHiTech/gohitech.core.git ~/.ansible/collections/ansible-collections/gohitech/core
```

## Development

### Submodules

```bash
# Setup submodules
git submodule add -b main git@github.com:dean-taylor/ansible-role-microk8s.git roles/microk8s
#git submodule update --init
git submodule update --remote

# Work with submodule
cd roles/microk8s
git checkout main

# Update parent module
git add roles/microk8s
git commit -m "Update submodule tracking to the latest commit"
```
