# Development Environment

- OS: Ubuntu

## Fresh Setup

```sh
ansible-playbook -t core,dotfiles --vault-password-file ~/vault.key local.yaml
```

### Encrypt .ssh files

```sh
 find .ssh -type f | xargs ansible-vault encrypt --vault-password-file ~/vault.key
```

### Decrypt .ssh files
```sh
 find .ssh -type f | xargs ansible-vault decrypt --vault-password-file ~/vault.key
```