sudo
=========

Installs and configures sudo (Debian and RedHat). Also manages sudoers.d directory with files. This role is merged from https://github.com/Rackor3000/ansible-sudo and https://github.com/knopki/ansible-sudoers, Rackor3000 and knopki are authors. Thanks them a lot! 

Requirements
------------

No requirements.

Role Variables
--------------

* sudo_defaults - list of defaults in sudoers file
* sudo_sudoers - list of users/groups in sudoers file
* sudo_sudoers_d - list of users/groups in sudoers.d directory

Dependencies
------------

No dependencies.

Example Playbook
----------------

        - hosts: all
          sudo: yes
          roles:
            - sudo
          vars:
            sudo_sudoers:
              - name: %sudo
                nopasswd: true
            sudo_sudoers_d:
              - name: user1
                hosts:
                  - ALL
                asusers:
                 - root
                nopasswd: true
                commands:
                  - /usr/bin/id
