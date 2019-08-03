Role Name
=========

Ansible role to deploy Webmin web-based linux administration utility.

Webmin service will be available on https://host:10000.

Default login will be the credentials of the installer user.

You may get a browser warning about Webmin's default self-sign SSL certificate.


Requirements
------------

Requires root privileges.

Role Variables
--------------

- `install_utilities`: False

Set to True to install various utility packages used by Webmin management functions (wget, git, ntpdate, sntp, smartmontools)

- `firewalld_enable`: False

Set to True to open port 10000 via firewalld (assumes firewalld is running)

- `iptables_enable`: False

Set to True to open port 10000 via iptables (assumes iptables is running)

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml

    - name: Provision webmin role
      hosts: all
      become: true
      become_user: root
      
      vars:
         firewalld_enable: False
         iptables_enable: False
         install_utilities: True

      roles:
      - semuadmin.webmin
```
     
License
-------

BSD

Author Information
------------------

semuadmin@noreply.user.github.com
