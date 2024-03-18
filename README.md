# Development Environment

### Encrypt .ssh files

```sh
 find .ssh -type f | xargs ansible-vault encrypt --vault-password-file ~/vault.key
```

### Decrypt .ssh files
```sh
 find .ssh -type f | xargs ansible-vault decrypt --vault-password-file ~/vault.key
```