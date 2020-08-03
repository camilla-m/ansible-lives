# ansible-lives

Listing all working modules: https://docs.ansible.com/ansible/latest/modules/list_of_all_modules.html

Examples building ansible hosts file with parameters: https://docs.ansible.com/ansible/latest/user_guide/intro_inventory.html

### First class

Installation | Troubleshooting | Setting static hosts with tips | Some modules | AWS Modules

### Second class

EC2 Modules | Boto | pip | Troubleshooting | Credentials | Python Version | Lauching Instances with Ansible | EC2 services | Security Group | Elastic Ip | Permissions | Host | Running in another instance a playbook 

Useful links: 

https://docs.aws.amazon.com/general/latest/gr/rande.html#ec2_region

https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html

https://stackoverflow.com/questions/45073617/how-to-install-pip-with-yum-on-ec2?rq=1

https://docs.ansible.com/ansible/latest/modules/ec2_group_module.html

https://docs.ansible.com/ansible/latest/modules/ec2_eip_module.html

### Third class

Creating vault | Editing vault | Encrypt vault | Decrypt vault | Multiple vaults | Ask pass vault | Vault pass file | Running playbook with vaults | DevSecOps

Working with ansible vaults. Commom commands:

`ansible-vault create awsvaults`

`ansible-vault edit awsvaults`

Playing playbook with vault (it will ask the vault pass you created):

`ansible-playbook site.yml --ask-vault-pass`

Selecting a vault password file in cmd line:

`ansible-playbook site.yml --vault-password-file awsvaults`

Selecting vault or more vaults inside playbook (check ec2 vaults playbook):

```
  vars_files:
    - awsvault
    - nametest  
```

Useful links:

https://docs.ansible.com/ansible/latest/user_guide/playbooks_vault.html

### Class 4th - Dynamic inventories

Useful commands:

```
ansible-inventory -i demo.aws_ec2.yml --graph
ansible-playbook playbook-inicial.yml -i demo.aws_ec2.yml
ansible-inventory -h
ansible-inventory -i demo.aws_ec2.yml --list
ansible-inventory -i demo.aws_ec2.yml --graph
/home/ec2-user/ec2.py --list
ansible -i ec2.py -u ec2-user us-east-2 -m ping
```






