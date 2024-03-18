# cl-ansible
Lab Cumulus and Ansible

```bash
ssh-keygen -f ssh/smc_key_rsa # creates pair
```

```bash
./clone.se
```

```bash
ubuntu@oob-mgmt-server:~/cl-ansible$ ansible-playbook site.yml
```

## onie

```bash
onie-nos-install http://192.168.200.1/onie-installer
```

### ztp

```bash
cumulus@onie:mgmt:~$ sudo ztp -v -r http://192.168.200.1/cumulus-ztp
```
