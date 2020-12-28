Ansible Role: package-update
=========

Role to update Debian, RHEL and CentOS packages.

Updates all packages except blacklisted, gracefully shutdown services and allow or not reboot if needed.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    allow_reboot: true

Allow or not rebooting if updating needs reboot.

    before_reboot_stop: []

List services to gracefully shutdown before reboot.

    hold_packages: []

List packages to hold = packages to not upgrade.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: all
      become: yes
      roles:
        - {role: r0mdau.package_update }

*Inside playbook `group_vars/all.yml`*:

    allow_reboot: false
    before_reboot_stop:
      - nginx
    hold_packages:
      - nginx

Scripts
-------
///TODO
```
ansible-playbook tests/test.yml -i tests/inventory --syntax-check
```

License
-------

Apache-2.0

Author Information
------------------

r0mdau[¹](https://github.com/r0mdau)
