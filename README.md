Ansible Role: Oh-My-Zsh
=======================

[![Build Status](https://travis-ci.org/gantsign/ansible-role-oh-my-zsh.svg?branch=master)](https://travis-ci.org/gantsign/ansible-role-oh-my-zsh)
[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-gantsign.oh--my--zsh-blue.svg)](https://galaxy.ansible.com/gantsign/oh-my-zsh)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/gantsign/ansible-role-oh-my-zsh/master/LICENSE)

Role to download, install and configure [Oh-My-Zsh](http://ohmyz.sh/).

Requirements
------------

* Ansible >= 2.4

* Linux Distribution

    * Debian Family

        * Debian

            * Jessie (8)
            * Stretch (9)

        * Ubuntu

            * Trusty (14.04)
            * Xenial (16.04)
            * Bionic (18.04)

    * RedHat Family

        * CentOS

            * 7

        * Fedora

            * 28

    * SUSE Family

        * openSUSE

            * 15.0

    * Note: other versions are likely to work but have not been tested.

Role Variables
--------------

The following variables will change the behavior of this role (default values
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

More Roles From GantSign
------------------------

You can find more roles from GantSign on
[Ansible Galaxy](https://galaxy.ansible.com/gantsign).

Development & Testing
---------------------

This project uses [Molecule](http://molecule.readthedocs.io/) to aid in the
development and testing; the role is unit tested using
[Testinfra](http://testinfra.readthedocs.io/) and
[pytest](http://docs.pytest.org/).

To develop or test you'll need to have installed the following:

* Linux (e.g. [Ubuntu](http://www.ubuntu.com/))
* [Docker](https://www.docker.com/)
* [Python](https://www.python.org/) (including python-pip)
* [Ansible](https://www.ansible.com/)
* [Molecule](http://molecule.readthedocs.io/)

Because the above can be tricky to install, this project includes
[Molecule Wrapper](https://github.com/gantsign/molecule-wrapper). Molecule
Wrapper is a shell script that installs Molecule and it's dependencies (apart
from Linux) and then executes Molecule with the command you pass it.

To test this role using Molecule Wrapper run the following command from the
project root:

```bash
./moleculew test
```

Note: some of the dependencies need `sudo` permission to install.

License
-------

MIT

Author Information
------------------

John Freeman

GantSign Ltd.
Company No. 06109112 (registered in England)
