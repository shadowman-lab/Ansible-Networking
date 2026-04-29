<!-- This was created with Claude Code -->

network_interface_config
========================

An Ansible role for network interface config.

Requirements
------------

- Ansible 2.9 or higher
- Access to target systems with appropriate permissions

Role Variables
--------------

* **state**: Variable used in: Update interfaces on ios
  - Default: `merged`

* **enabled**: Variable used in: GigabitEthernet2
  - Default: `expose_to_cloud_redhat_com_results`

Dependencies
------------

None

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: network_interface_config
      vars:
        state: <value>
        enabled: <value>
```

License
-------

GNU General Public License v3.0 or later

Author Information
------------------

Red Hat Ansible Automation Platform
