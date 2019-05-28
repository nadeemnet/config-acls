# config-acls
This Ansible playbook configures/changes ACLs on Cisco  nx-os switches. In order to modify ACLs edit the file acl_config.yaml. Only the entries under variable 'lines' shoud be changed.

## How to run playbook

ansible-playbook push_acls.yaml

To see what changes will be made to switches without pushing these commands.

ansible-playbook push_acls.yaml --check -v
