Ansible challenge
===

This playbook is used for:
- provisioning an ubuntu 16.04 instance alongside appropriate security group.
- deploying a simple web-app with a web-page that is showing the local IP address of the newly created instance.

**IMPORTANT:**  
This playbook uses roles structure (two roles), please notice 'vars' inside the playbook for configuration flexability (override).  
- REQUIRED variables (inserted by the user):
  - local_pc_public_ip
  - ansible_public_ip

  The rest of the variables have default values in *roles/provision/defaults/main.yml* file.
- Another important variable is 'key_name', the 'provision' role will look for 'key_name' under '~/.ssh' directory  
  in order to generate keypair & upload to AWS for later SSH usage.  
  Default = 'my_aws'.

**Playbook usage:**  
To activate this playbook:  
> ansible-playbook playbook.yml


**Log file:** /var/log/ansible.log 
