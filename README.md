# Ansible Collection - gohitech.core

Documentation for the collection.

## Deploy

```bash
ansible-galaxy collection install https://github.com/GoHiTech/gohitech.core/releases/download/v0.2.5/gohitech-core-0.2.5.tar.gz
```

requirements.yml

```yaml
collections:
  - name: gohitech.core
    source: https://github.com/GoHiTech/gohitech.core/releases/download/v0.2.5/gohitech-core-0.2.5.tar.gz
    type: url
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
