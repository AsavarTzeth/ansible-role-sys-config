[![Build Status](https://travis-ci.org/AsavarTzeth/ansible-role-sys-config.svg?branch=master)](https://travis-ci.org/AsavarTzeth/ansible-role-sys-config)

Ansible Users Role - ansible-role-sys-config
============================================

**Ansible role that manages basic system configuration.**

To be more specific the goal of this role is to cover things like
hostname, locale, time-zone; things that usually are part of the
operating system installer.

Requirements
------------

This role was developed and tested on Ansible 2.2.0 and higher.
It may work on lower versions but that is currently unsupported.

Role Variables
--------------

    # Sets the system time zone
    sys_config_timezone:     (default: Europe/Stockholm)

    # Sets various system localization settings
    sys_config_locale_lang:  (default: sv_SE.UTF-8)
    sys_config_vc_keymap:    (default: sv-latin1)

    # Sets system hostname (useful on local connection)
    sys_config_hostname:     (default: {{ inventory_hostname }})


Dependencies
------------

None

Example Playbook
----------------

1) Set various basic system settings

    - hosts: all
      roles:
        - role: AsavarTzeth.sys-config
          sys_config_timezone: United States/Pacific
          sys_config_locale_lang: en_US.UTF-8
          sys_config_vc_keymap: us

License
-------

BSD-2-Clause

Author Information
------------------

Patrik Nilsson
