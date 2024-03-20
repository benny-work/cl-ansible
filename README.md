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

### dhcp, isc-dhcp-server at oob-mgmt-server

Snippet from `/etc/dhcp/dhcpd.conf`

```bash
...
option www-server code 72 = ip-address;
option cumulus-provision-url code 239 = text;

...

# OOB Management subnet
shared-network LOCAL-NET{
subnet 192.168.200.0 netmask 255.255.255.0 {
  range 192.168.200.10 192.168.200.50;
  option domain-name-servers 192.168.200.1;
  option domain-name "simulation";
  default-lease-time 172800;  #2 days
  max-lease-time 345600;      #4 days
  option www-server 192.168.200.1;
  option default-url = "http://192.168.200.1/onie-installer";
  option cumulus-provision-url "http://192.168.200.1/cumulus-ztp";
  option ntp-servers 192.168.200.1;
}
}
...
```

Test the configuration file.
```bash
root@oob-mgmt-server:~# dhcpd -t -cf /etc/dhcp/dhcpd.conf
```

### ztp script

```bash
cumulus@onie:mgmt:~$ sudo ztp -v -r http://192.168.200.1/cumulus-ztp  # run ztp
```
