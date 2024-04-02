# Development Environment

Ansible playbook to setup my WSL2 based Ubuntu workspace.

## Bootstrap

Oneliner to bootstrap the development environment

```sh
curl -fsSL "https://raw.githubusercontent.com/tanishqmanuja/devenv/main/bootstrap" | sh 
```

Using specific tags like nvim for example

```sh
curl -fsSL "https://raw.githubusercontent.com/tanishqmanuja/devenv/main/bootstrap" | sh -s -- nvim
```

## Other Commands

#### Run Playbook

```sh
ansible-playbook -t core,dotfiles --ask-become-pass --vault-password-file ~/vault.key local.yaml
```

#### Encrypt files in .ssh directory

```sh
 find .ssh -type f | xargs ansible-vault encrypt --vault-password-file ~/vault.key
```

#### Decrypt files in .ssh directory
```sh
 find .ssh -type f | xargs ansible-vault decrypt --vault-password-file ~/vault.key
```