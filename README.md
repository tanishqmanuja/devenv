# Development Environment

Ansible playbook to setup my WSL2 bases Ubuntu workspace.

### Bootstrap

```sh
curl -fsSL "https://raw.githubusercontent.com/tanishqmanuja/devenv/main/bootstrap" | bash 
```

### Bootstrap (with tags)

```sh
curl -fsSL "https://raw.githubusercontent.com/tanishqmanuja/devenv/main/bootstrap" | bash -s -- nvim
```

### Run Playbook

```sh
ansible-playbook -t core,dotfiles --ask-become-pass --vault-password-file ~/vault.key local.yaml
```

### Encrypt .ssh files

```sh
 find .ssh -type f | xargs ansible-vault encrypt --vault-password-file ~/vault.key
```

### Decrypt .ssh files
```sh
 find .ssh -type f | xargs ansible-vault decrypt --vault-password-file ~/vault.key
```