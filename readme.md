Ansible challenge
===

This playbook has two roles and it is used for:
- provisioning an ubuntu 16.04 instance alongside appropriate security group.
- deploying a simple web-app with a web-page that is showing the IP address of the local IP address of the newly created instance.

**IMPORTANT:**  
This playbook uses roles structure, please notice 'vars' inside the playbook for configuration flexability.  
- REQUIERED variables (input by the user):
  - local_pc_public_ip
  - ansible_internal_ip

  The rest of the variables have default values in *roles/provision/defaults/main.yml* file.
- Another important variable is 'key_name', the 'provision' role will look for 'key_name' under '~/.ssh' directory  
  for keypair creation & upload to AWS for later SSH usage. Default = 'my_aws'.

**Playbook usage:**  
To activate this playbook:  
> ansible-playbook playbook.yml