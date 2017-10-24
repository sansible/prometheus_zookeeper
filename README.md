# prometheus_zookeeper_exporter

Master: [![Build Status](https://travis-ci.org/sansible/prometheus_zookeeper_exporter.svg?branch=master)](https://travis-ci.org/sansible/prometheus_zookeeper_exporter)  
Develop: [![Build Status](https://travis-ci.org/sansible/prometheus_zookeeper_exporter.svg?branch=develop)](https://travis-ci.org/sansible/prometheus_zookeeper_exporter)

* [ansible.cfg](#ansible-cfg)
* [Installation and Dependencies](#installation-and-dependencies)
* [Tags](#tags)
* [Examples](#examples)

This roles installs Prometheus Zookeeper Exporter.

Prometheus Zookeeper Exporter makes available system metrics for collection by Prometheus server.

For more information about Prometheus Zookeeper Exporter please visit
[https://github.com/carlpett/zookeeper_exporter](https://github.com/carlpett/zookeeper_exporter).

For more information about Prometheus Server please visit
[https://prometheus.io](https://prometheus.io).


## ansible.cfg

This role is designed to work with merge "hash_behaviour". Make sure your
ansible.cfg contains these settings

```INI
[defaults]
hash_behaviour = merge
```




## Installation and Dependencies

This role will install `sansible.users_and_groups` for managing `prometheus_zookeeper_exporter` user.

To install run `ansible-galaxy install sansible.prometheus_zookeeper_exporter` or add this to your
`roles.yml`.

```YAML
- name: sansible.prometheus_zookeeper_exporter
  version: v1.0
```

and run `ansible-galaxy install -p ./roles -r roles.yml`




## Tags

This role uses tags: **build** and **configure**

* `build` - Installs Prometheus Zookeeper Exporter and all it's dependencies.
* `configure` - Configure Prometheus Zookeeper Exporter and all it's dependencies.


## Examples

Simply include role in your playbook

```YAML
- name: Install and configure prometheus_zookeeper_exporter
  hosts: "somehost"

  roles:
    - role: sansible.prometheus_zookeeper_exporter
```

```YAML
- name: Install and configure prometheus_zookeeper_exporter and enable start on boot.
  hosts: "somehost"

  roles:
    - role: sansible.prometheus_zookeeper_exporter
      sansible_prometheus_zookeeper_exporter:
        start_on_boot: yes
```
