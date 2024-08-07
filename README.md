# Ansible
Steps to execute playbook:
#
1.Install Ansible based on your os
#
3. Install boto packages using pip: pipx install boto boto3
#
4. Create directory from your Ansible project directory to store AWS access keys. I have already did it. So, if you clone my code ignore this step: mkdir -p group_vars/all/
#
5. Create a hashed password file vault.pass in the project root directory. I have already did it. So, if you clone my code ignore this step: openssl rand -base64 2048 > vault.pass
#
6. Create an ansible vault. 'vault.pass' is referenced with '--vault-password-file' option. This opens up the 'vim' editor, press 'i' or 'a' to edit, then 'esc' ':wq' to save and exit
Add this text in using your own access and secret key
ec2_access_key: AAAAAAAAAAAAAABBBBBBBBBBBB                                      
ec2_secret_key: afjdfadgf$fgajk5ragesfjgjsfdbtirhf.
I have already did it. So, if you clone my code ignore this step: ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass
#
7. Execute Playbook: ansible-playbook ./playbooks/main.yml -e @group_vars/all/pass.yml --vault-password-file=vault.pass

