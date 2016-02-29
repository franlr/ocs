ansible-ocs
=========

[![Ansible Galaxy](https://img.shields.io/badge/galaxy-franlr--ocs-blue.svg)](https://galaxy.ansible.com/list#/roles/4468)

An Ansible role for installing ocsinventory-agent.

This role only works with the ocsinventory-agent 2.1 or later to let the agent be installed non-interactively (http://wiki.ocsinventory-ng.org/index.php/Documentation:UnixAgent).

Tested on:
- Debian 7
- CentOS 6

Requirements
------------

None.
 
Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
ocs_name: Ocsinventory-Unix-Agent
ocs_stable_version: 2.1
ocs_agent_version: 2.1
ocs_pkg: Ocsinventory-Unix-Agent-{ocs_agent_version}.tar.gz
ocs_pkgreqs: (see `vars/{{ ansible_os_family }}.yml
ocs_down_dir: /tmp
ocs_down_url: https://launchpad.net/ocsinventory-unix-agent/stable-{ocs_stable_version}/{ocs_agent_version}/+download/
ocs_server: ocsinventory-server.domain.name
ocs_basedir: /var/lib/ocsinventory-agent
ocs_configdir: /etc/ocsinventory
ocs_tag: srvtype
ocs_logfile: /var/log/ocsinventory-agent.log
ocs_options: --crontab --remove-old-linux-agent --debug --nossl --download --snmp --now
```

Dependencies
------------

Development tools and perl dependencies are included into roles's requirements. This role installs and uses CPAN to install perl 'Digest::MD5'.

Example Playbook
----------------

How to use this role:

``` yml
---
- hosts: all
  gather_facts: true
  sudo: no
  user: root
  roles:
    - { role: "franlr.ocs", ocs_server: "your-ocsinventory-server.domain.name", ocs_tag: "your-tag" }
```

License
-------

Apache v2.0

Author Information
------------------

This role was created in 2015 by [FranLR](https://github.com/franlr/)
