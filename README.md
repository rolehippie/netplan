# netplan

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/netplan) [![Testing Build](https://github.com/rolehippie/netplan/workflows/testing/badge.svg)](https://github.com/rolehippie/netplan/actions?query=workflow%3Atesting) [![Readme Build](https://github.com/rolehippie/netplan/workflows/readme/badge.svg)](https://github.com/rolehippie/netplan/actions?query=workflow%3Areadme) [![Galaxy Build](https://github.com/rolehippie/netplan/workflows/galaxy/badge.svg)](https://github.com/rolehippie/netplan/actions?query=workflow%3Agalaxy) [![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/netplan)](https://github.com/rolehippie/netplan/blob/master/LICENSE) 

Ansible role to install and configure netplan networking. 

## Sponsor 

[![Proact Deutschland GmbH](https://proact.eu/wp-content/uploads/2020/03/proact-logo.png)](https://proact.eu) 

Building and improving this Ansible role have been sponsored by my employer **Proact Deutschland GmbH**.

## Table of content

* [Default Variables](#default-variables)
  * [netplan_bonds](#netplan_bonds)
  * [netplan_bridges](#netplan_bridges)
  * [netplan_config_file](#netplan_config_file)
  * [netplan_ethernets](#netplan_ethernets)
  * [netplan_renderer](#netplan_renderer)
  * [netplan_version](#netplan_version)
  * [netplan_vlans](#netplan_vlans)
* [Dependencies](#dependencies)
* [License](#license)
* [Author](#author)

---

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

## Dependencies

* None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
