Ansible Role: Oh-My-Zsh
=======================

[![Build Status](https://travis-ci.org/gantsign/ansible-role-oh-my-zsh.svg?branch=master)](https://travis-ci.org/gantsign/ansible-role-oh-my-zsh)

Role to download, install and configure [Oh-My-Zsh](http://ohmyz.sh/).

Requirements
------------

* Ubuntu

Role Variables
--------------

The following variable will change the behavior of this role (default values
are shown below):

```yaml
# Default theme
oh_my_zsh_theme: robbyrussell

# Default plugins
oh_my_zsh_plugins:
  - git

# User configuration
# Important: oh-my-zsh is installed per user so you need to specify the users to install it for.
users:
  - username: example1
    oh_my_zsh:
      theme: robbyrussell
      plugins:
        - git
  - username: example2
    oh_my_zsh:
      theme: robbyrussell
      plugins:
        - git
        - mvn
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
    - role: gantsign.oh-my-zsh
      users:
        - username: example
```

License
-------

MIT

Author Information
------------------

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)
