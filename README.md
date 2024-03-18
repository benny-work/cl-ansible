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

if dhcp is not working

```bash
ONIE: Using link-local IPv4 addr: eth0: 169.254.204.236/16  # 255.255.0.0
```

```bash
ONIE:/ # ip link show eth0  # show mac (for dhcpd)
ONIE:/ # onie-nos-install http://192.168.200.1/onie-installer
```

### ztp script

```bash
cumulus@onie:mgmt:~$ sudo ztp -v -r http://192.168.200.1/cumulus-ztp  # test ztp
```
