# netplan

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/netplan)
[![General Workflow](https://github.com/rolehippie/netplan/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/netplan/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/netplan/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/netplan/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/netplan/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/netplan/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/netplan)](https://github.com/rolehippie/netplan/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.netplan-blue)](https://galaxy.ansible.com/rolehippie/netplan)

Ansible role to install and configure netplan networking.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [netplan_bonds](#netplan_bonds)
  - [netplan_bridges](#netplan_bridges)
  - [netplan_config_file](#netplan_config_file)
  - [netplan_ethernets](#netplan_ethernets)
  - [netplan_renderer](#netplan_renderer)
  - [netplan_rts](#netplan_rts)
  - [netplan_version](#netplan_version)
  - [netplan_vlans](#netplan_vlans)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### netplan_bonds

Definition of bond entries

#### Default value

```YAML
netplan_bonds:
```

#### Example usage

```YAML
netplan_bonds:
  bond0:
    mode: balance-rr
    interfaces:
      - enp6s0
      - enp6s1
```

### netplan_bridges

Definition of bridge entries

#### Default value

```YAML
netplan_bridges:
```

#### Example usage

```YAML
netplan_bridges:
  virbr1:
    dhcp4: True
    dhcp4-overrides:
      use-routes: False
    interfaces:
      - vlan905
```

### netplan_config_file

Path to config written to

#### Default value

```YAML
netplan_config_file: /etc/netplan/01-netcfg.yaml
```

### netplan_ethernets

Definition of ethernet entries

#### Default value

```YAML
netplan_ethernets:
```

#### Example usage

```YAML
netplan_ethernets: |
  enp6s0:
    dhcp4: True
```

### netplan_renderer

Renderer used by netplan

#### Default value

```YAML
netplan_renderer: networkd
```

### netplan_rts

Define the available routing tables

#### Default value

```YAML
netplan_rts: []
```

#### Example usage

```YAML
netplan_rts:
  - id: 255
    name: local
  - id: 254
    name: main
  - id: 253
    name: default
  - id: 0
    name: unspec
```

### netplan_version

Version of the netplan config format

#### Default value

```YAML
netplan_version: '2'
```

### netplan_vlans

Definition of vlan entries

#### Default value

```YAML
netplan_vlans:
```

#### Example usage

```YAML
netplan_vlans:
  vlan905:
    id: 905
    dhcp4: True
    link: enp6s0
```

## Discovered Tags

**_netplan_**


## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
