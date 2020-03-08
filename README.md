# netplan

[![Build Status](https://cloud.drone.io/api/badges/rolehippie/netplan/status.svg)](https://cloud.drone.io/rolehippie/netplan)

Ansible role to configure netplan

## Table of content

* [Default Variables](#default-variables)
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

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
