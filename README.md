# Ansible Role: package_update

An ansible role to update all packages (multiplatform)

## Requirements

### Supported platforms

* Archlinux
* Debian
* FreeBSD
* NetBSD
* OpenBSD
* RedHat
* Suse

## Role Variables
### OS related variables

The following variables are set by the role.

* **freebsd_running_jails**: List with the running FreeBSD jails.

### Playbook related variables

* **package_update**: "name space"
  * **freebsd**: "freebsd config" 
    * **get_running_jails**: no | yes (default) set the freebsd_running_jails variable.
    * **host**: no | yes (default) update the host system
    * **jails**: Array of jails to update, **freebsd_running_jails** by default.
    

## Dependencies

None

## Example Playbooks

### Upgrade

```
---
- name: update packages
  hosts: all
  become: true
  roles:
    - stafwag.package_update
```

### Update only the FreeBSD host systems. 

```
---
- name: update packages
  hosts: all
  become: true
  roles:
    - role: stafwag.package_update
      vars:
        package_update:
          freebsd:
            get_running_fails: no
            jails: []
```

### Update only the running jails on FreeBSD systems.

```
---
- name: update packages
  hosts: all
  become: true
  roles:
    - role: stafwag.package_update
      vars:
        package_update:
          freebsd:
            host: no
```

### Update a jail on a  FreeBSD system.

```
---
- name: update packages
  hosts: rataplan
  become: true
  roles:
    - role: stafwag.package_update
      vars:
        package_update:
          freebsd:
            host: no
            jails:
              - stafmail

```


## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be
