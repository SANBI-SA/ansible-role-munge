### Install Munge on a node

Many components of this are copied from [this role](https://github.com/grycap/ansible-role-munge) (which is released under the Apache Public License 2.0).

The munge key for SANBI is stored in Vault at the key `secret/ansible/slurm/munge_base64` in base64 encoded form. To use this as a Ansible variable, you 
could use `munge_key: "{{ lookup('hashi_vault', 'secret=secret/ansible/slurm:munge_base64') | b64decode }}"`.