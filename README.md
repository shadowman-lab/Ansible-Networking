<!-- This was created with Claude Code -->

# Networking Automation

[![Contribute](https://img.shields.io/badge/OpenShift-Dev%20Spaces-525C86?logo=redhatopenshift&labelColor=EE0000)](https://devspaces.apps.ocp.shadowman.dev/#https://github.com/shadowman-lab/Ansible-Networking)


This directory contains Ansible automation for networking management and operations.

## Overview

The Networking automation provides playbooks and roles for managing and configuring
networking infrastructure and services.

## Roles

| Role | Description |
| ---- | ----------- |
| [network_arista_podman](roles/network_arista_podman/README.md) | Role for network arista podman |
| [network_backup](roles/network_backup/README.md) | Role for network backup |
| [network_backup_git_collection](roles/network_backup_git_collection/README.md) | Role for network backup git collection |
| [network_base_config](roles/network_base_config/README.md) | Role for network base config |
| [network_base_full](roles/network_base_full/README.md) | Role for network base full |
| [network_base_min](roles/network_base_min/README.md) | Role for network base min |
| [network_base_vars](roles/network_base_vars/README.md) | Role for network base vars |
| [network_create_restore](roles/network_create_restore/README.md) | Role for network create restore |
| [network_create_restore_collection](roles/network_create_restore_collection/README.md) | Role for network create restore collection |
| [network_facts_gather](roles/network_facts_gather/README.md) | Role for network facts gather |
| [network_facts_push](roles/network_facts_push/README.md) | Role for network facts push |
| [network_interface_config](roles/network_interface_config/README.md) | Role for network interface config |
| [network_interface_remediate](roles/network_interface_remediate/README.md) | Role for network interface remediate |
| [network_ios_remove_syslog](roles/network_ios_remove_syslog/README.md) | Role for network ios remove syslog |
| [network_ios_upgrade](roles/network_ios_upgrade/README.md) | Role for network ios upgrade |
| [network_operational_state](roles/network_operational_state/README.md) | Role for network operational state |
| [network_restore](roles/network_restore/README.md) | Role for network restore |
| [network_update_password](roles/network_update_password/README.md) | Role for network update password |
| [network_version](roles/network_version/README.md) | Role for network version |
| [network_vxlan_config](roles/network_vxlan_config/README.md) | Role for network vxlan config |
| [ocp_dns](roles/ocp_dns/README.md) | Role for ocp dns |

## Playbooks

| Playbook | Description | Target Hosts |
| -------- | ----------- | ------------ |
| backup_cisco_git_collection.yml | Playbook for backup cisco git collection | os_cisco, os_cisco |
| backup_collections.yml | Playbook for backup collections | tag_Router, report.shadowman.dev |
| backup_network_git.yml | Playbook for backup network git | all, all |
| baseconfig.yml | Playbook for baseconfig | {{ device_name | default('all')}} |
| builddevicereport.yml | Playbook for builddevicereport | all |
| fulldevicefacts.yml | Playbook for fulldevicefacts | all |
| ios_interface_config.yml | Playbook for ios interface config | all |
| ios_logging.yml | Playbook for ios logging | os_cisco |
| ios_upgrade.yml | Playbook for ios upgrade | os_cisco, report.shadowman.dev, os_cisco |
| network_base.yml | Playbook for network base | all |
| network_base_vars.yml | Playbook for network base vars | all |
| network_interface_remediate.yml | Playbook for network interface remediate | {{ device | default('all') }} |
| network_min.yml | Playbook for network min | all |
| network_operational_state.yml | Playbook for network operational state | os_cisco |
| network_restore.yml | Playbook for network restore | all |
| network_vxlan_config.yml | Playbook for network vxlan config | all |
| networking_drift_check.yml | Playbook for networking drift check | all |
| ocp_dns.yml | Playbook for ocp dns | localhost |
| passwordupdate.yml | Playbook for passwordupdate | all |
| podman_arista.yml | Playbook for podman arista | all |
| resourcefactspush.yml | Playbook for resourcefactspush | all |
| setup_eos_container.yml | Playbook for setup eos container | all |
| showversion.yml | Playbook for showversion | all |

## Usage

### Running with ansible-navigator

```bash
# Run a playbook
ansible-navigator run backup_cisco_git_collection.yml

# Run in stdout mode
ansible-navigator run backup_cisco_git_collection.yml -m stdout
```

### Using roles

```yaml
- hosts: target_hosts
  roles:
    - network_arista_podman
```

## Requirements

- Ansible 2.9 or higher (via ansible-navigator)
- Required collections (see `collections/requirements.yml` if present)
- Appropriate access credentials configured via environment variables

## Directory Structure

```
Ansible-Networking/
├── roles/              # Ansible roles
├── *.yml               # Playbooks
├── collections/        # Collection dependencies (if present)
└── ansible-navigator.yml  # Navigator configuration
```
