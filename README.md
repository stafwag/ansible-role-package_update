# Ansible Role: package_update

Update all packages (multiplatform)

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

None

## Dependencies

None

## Example Playbook

```
---
- name: update packages
  hosts: all
  become: true
  roles:
    - stafwag.package_update
```

## License

MIT/BSD

## Author Information

Created by Staf Wagemakers, email: staf@wagemakers.be, website: http://www.wagemakers.be
