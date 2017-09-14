[![License: Apache 2.0](https://img.shields.io/badge/license-Apache--2.0-blue.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)

[![Build Status](https://travis-ci.org/LasLabs/ansible-linux-active-directory.svg?branch=master)](https://travis-ci.org/LasLabs/ansible-linux-active-directory)

Active Directory for Linux Servers
==================================

This role will allow you to provision a Debian or Fedora Based box with an
 Active Directory login backend.

Usage
=====

Requirements
------------

There are no prerequisites.

Role Variables
--------------
| Name | Description |
| :--: | :---------: |
| ldap_description | A description of this connection for SSSD. |
| ldap_server_ip | The IP Address of the desired AD DC. Comma separated values are allowed. |
| ldap_domain | The FQDN of your Windows Domain. |
| ldap_server | The FQDN of the AD DC server. Comma separated values are allowed here too. |
| ldap_bind_dn | The user to bind to the directory with. A user principle name is recommended. |
| ldap_bind_pw | The password for the bind user. |
| ldap_user_base | The top level DN of your AD where users are stored. |
| ldap_group_base | The top level DN of your AD where groups are stored. |

Dependencies
------------

There are no dependencies.

Example Playbook
----------------

```
    - hosts: servers
      roles:
         - { role: active-directory.role,
             ldap_description: AD DC,
             ldap_server_ip: 10.0.0.1,
             ldap_domain: corp.example.com,
             ldap_server: ex-dc-prod-vmw-01.corp.example.com,
             ldap_bind_dn: svc.ro-bind@corp.example.com,
             ldap_bind_pw: somepasswd,
             ldap_user_base: OU=Example,DC=corp,DC=example,DC=com,
             ldap_group_base: OU=Groups,OU=Example,DC=corp,DC=example,DC=com }
```

Credits
=======

Contributors
------------

* Ted Salmon <tsalmon@laslabs.com>

Maintainer
----------

[![LasLabs Inc.](https://laslabs.com/logo.png)](https://laslabs.com)

This module is maintained by [LasLabs Inc.](https://laslabs.com)

* https://github.com/laslabs/ansible-linux-active-directory
