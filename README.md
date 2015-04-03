hostname
========

Ansible role which helps to set custom hostname as a class call.


Example
-------

```
---

# Example of the basic usage
- hosts: myhost
  roles:
    - hostname

# Example of how to ser a custom hostname
- hosts: myhost
  roles:
    - role: hostname
      hostname_string: myhostname
```

You can also put some logic into the variable. For example use the invenotry
hostname when the host is a VM run by VirtualBox:

```
---

- hosts: myhost
  roles:
    - role: hostname
      hostname_string: "{{ inventory_hostname if ansible_virtualization_role == 'guest' and ansible_virtualization_type == 'virtualbox' else '' }}"
```


Role variables
--------------

List of variables used by the role:

```
# Description and default value of the variable
hostname_string: "{{ inventory_hostname }}"
```


License
-------

MIT


Author
------

Jiri Tyr
