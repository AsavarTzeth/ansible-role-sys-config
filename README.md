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
    sys_config_timezone:   (default: Europe/Stockholm)

    # Sets if rtc time will be stored in utc or localtime
    # By default nothing is changed.
    sys_config_rtc:        (undefined by default) (values: UTC or local)

    # Sets the locales to generate on the system, if the host
    # supports it. The first list entry will set the $LANG value.
    sys_config_locale:     (default: ['sv_SE.UTF-8','en_US.UTF-8'])

    # Sets the virtual console keymap
    sys_config_vc_keymap:  (default: sv-latin1)

    # Sets system hostname. Note, if your inventory uses localhost or an
    # ip address, use this or use ansible_host.
    sys_config_hostname:   (default: {{ inventory_hostname }})


Dependencies
------------

None

Example Playbook
----------------

Set various basic system settings

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
