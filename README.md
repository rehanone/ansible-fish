ansible-fish
=========

An ansible role for managing the installation of `fish` shell.

More information on `fish` shell can be found at:

  - [https://fishshell.com/](https://fishshell.com/)


Requirements
------------

This role requires `fish`  package to be avalible in package manager on the target system.

Role Variables
--------------

The following variables will change the behavior of this role (default values
are shown below):

```yaml
# Allows logging of the final configuration dictionary with all defaulted values which can be helpful for debugging
# Default value for debug is false
fish_debug: false

# Whether or not to install or remove fish
# choices: [ present, absent ]
# default: present
fish_state: present

# The os specific package name used to install fish
fish_package_name: fish

```

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: rehanone.fish
      vars:
        fish:
          debug: true
          state: present
          package_name: fish
          users:
          - name: ray
            state: present
            manage: true
          - name: dora
            state: present
            manage: true
      when: fish_manage
```

License
-------

Apache-2.0
