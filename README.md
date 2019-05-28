# config-acls
This Ansible playbook configures/changes ACLs on Cisco nx-os switches. The idea is that all acls modifications should be done via version controloed repository. The ACL names are standardized using vlan-id. Pushing ACL changes through Ansible playbook will minimize human error and version control will provide a clear understanding of when a particular change was made. The playbook is idempotent which means that ACLs will only be pushed if there is a change.

The respository has two files. 

1) acl_config.yaml
This is where you will introduce changes to the ACLS. Only the entries under variable 'lines' shoud be changed. 

2) push_acls.yaml
This is the playbook that pushes the acl changes using nxos_config module. 

## How to run playbook

ansible-playbook push_acls.yaml

To see what changes will be made to switches without pushing these commands.

ansible-playbook push_acls.yaml --check -v
