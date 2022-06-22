# Ansible Collection - gohitech.core

Documentation for the collection.

## Deploy using git clone

The Collection is using Git Submodules with SSH reference for team development.
If you do not have SSH keys for the project the submodule pull request will fail.
The following steps will allow the operation to function as expected.

```bash
# Clone the parent directory only
mkdir -p ~/.ansible/collections/ansible-collections/gohitech
git clone https://github.com/GoHiTech/gohitech.core.git ~/.ansible/collections/ansible-collections/gohitech/core

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
