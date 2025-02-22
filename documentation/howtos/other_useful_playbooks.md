# Optional but Useful Playbooks

This document describes a list of playbooks for optional tasks.

## Set applications user/group mapping to All Authenticated
This playbook is useful when removing anonymous access from Connections apps.  
To set roles to "All Authenticated in Application's Realm", add the following to the inventory
```
restrict_reader_access:  true
```
To set roles to "All Authenticated in Trusted Realms", add the following to the inventory
```
restrict_reader_access__trusted_realms:  true
```
then run this playbook:
```
ansible-playbook -i environments/examples/cnx7/connections playbooks/hcl/connections-restrict-access.yml
```
