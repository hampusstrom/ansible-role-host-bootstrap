Ansible Role: Host Bootstrap
=========

An ansible role that installs the host side dependencies for common ansible modules to work.
Can for example be ran against minimal debian installations, that don't include python before running your other plays/roles.


## Installation
### ansible-galaxy Soon (tm)
```
NotImplementedException on line 1: ansible-galaxy install hampusstrom.host_bootstrap
```

### Manual Installation
Current user only:
```
git clone https://github.com/hampusstrom/ansible-role-headscale.git ~/.ansible/roles/hampusstrom.host_bootstrap
```
System wide:
```
git clone https://github.com/hampusstrom/ansible-role-headscale.git /etc/ansible/roles/hampusstrom.host_bootstrap
```

Requirements
------------

### Init system(s): **any**
### Root required: **yes**

Since we require root, use this role in a playbook that has `become:yes` globally defined or call this role using the `become: yes` keyword.
```yaml
- hosts: my_hosts_with_no_python
  become: yes
  roles:
    - role: hampusstrom.host_bootstrap

# OR

- hosts: my_hosts_with_no_python
  roles:
    - role: hampusstrom.host_bootstrap
      become: yes
```

Role Variables
--------------

N/A

Dependencies
------------

N/A

Example Playbook
----------------


```yaml
---
- hosts: my_hosts_with_no_python
  become: true
  become_method: su
  become_flags: "-"
  gather_facts: false
  roles:
    - hampusstrom.host_bootstrap

```

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
