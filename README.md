# cl-ansible
Lab Cumulus and Ansible

```bash
ssh-keygen -f ssh/smc_key_rsa # creates pair
```

```bash
git clone https://github.com/benny-work/cl-ansible.git
ubuntu@oob-mgmt-server:~$ cd cl-ansible/
ubuntu@oob-mgmt-server:~/cl-ansible$ chmod 0600 ssh/smc_key_rsa
ansible -i inventory.yml -m ping -v all
```
