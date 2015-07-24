ansible-ocs
=========

An Ansible role for installing ocsinventory-agent.

This role only works with the ocsinventory-agent 2.1 or later to let the agent be installed non-interactively (http://wiki.ocsinventory-ng.org/index.php/Documentation:UnixAgent).

Tested on:
- Debian 7
- CentOS 6

Requirements
------------


Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

Example Playbook
----------------

How to use this role:

    - hosts: servers
      roles:
         - { role: franlr.ocs, ocs_server: ocsinventoryserver.domain.name, ocs_tagname: production }

License
-------

Apache v2.0

Author Information
------------------

