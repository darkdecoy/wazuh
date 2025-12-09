# Ansible Playbook - Wazuh indexer

Installing and maintaining Wazuh indexer.

## Table of content

- [Default Variables](#default-variables)
  - [wazuh_dashboard_password](#wazuh_dashboard_password)
  - [wazuh_domain_name](#wazuh_domain_name)
  - [wazuh_generate_certs](#wazuh_generate_certs)
  - [wazuh_indexer_admin_password](#wazuh_indexer_admin_password)
  - [wazuh_indexer_cluster_name](#wazuh_indexer_cluster_name)
  - [wazuh_indexer_cluster_nodes](#wazuh_indexer_cluster_nodes)
  - [wazuh_indexer_conf_path](#wazuh_indexer_conf_path)
  - [wazuh_indexer_custom_user](#wazuh_indexer_custom_user)
  - [wazuh_indexer_custom_user_role](#wazuh_indexer_custom_user_role)
  - [wazuh_indexer_discovery_nodes](#wazuh_indexer_discovery_nodes)
  - [wazuh_indexer_http_port](#wazuh_indexer_http_port)
  - [wazuh_indexer_index_path](#wazuh_indexer_index_path)
  - [wazuh_indexer_jvm_xms](#wazuh_indexer_jvm_xms)
  - [wazuh_indexer_network_host](#wazuh_indexer_network_host)
  - [wazuh_indexer_node_data](#wazuh_indexer_node_data)
  - [wazuh_indexer_node_ingest](#wazuh_indexer_node_ingest)
  - [wazuh_indexer_node_master](#wazuh_indexer_node_master)
  - [wazuh_indexer_node_name](#wazuh_indexer_node_name)
  - [wazuh_indexer_nolog_sensible](#wazuh_indexer_nolog_sensible)
  - [wazuh_indexer_sec_plugin_conf_path](#wazuh_indexer_sec_plugin_conf_path)
  - [wazuh_indexer_sec_plugin_tools_path](#wazuh_indexer_sec_plugin_tools_path)
  - [wazuh_indexer_start_timeout](#wazuh_indexer_start_timeout)
  - [wazuh_indexer_version](#wazuh_indexer_version)
  - [wazuh_local_certs_path](#wazuh_local_certs_path)
  - [wazuh_minimum_master_nodes](#wazuh_minimum_master_nodes)
  - [wazuh_perform_installation](#wazuh_perform_installation)
  - [wazuh_single_node](#wazuh_single_node)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## OS Requirements

This role is compatible with:

* Red Hat

* CentOS

* Fedora

* Debian

* Ubuntu



## Default Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):


### wazuh_dashboard_password

#### Default Value

```YAML
wazuh_dashboard_password: changeme
```

### wazuh_domain_name

#### Default Value

```YAML
wazuh_domain_name: wazuh.com
```

### wazuh_generate_certs

#### Default Value

```YAML
wazuh_generate_certs: true
```

### wazuh_indexer_admin_password

#### Default Value

```YAML
wazuh_indexer_admin_password: changeme
```

### wazuh_indexer_cluster_name

#### Default Value

```YAML
wazuh_indexer_cluster_name: wazuh
```

### wazuh_indexer_cluster_nodes

#### Default Value

```YAML
wazuh_indexer_cluster_nodes:
  - 127.0.0.1
```

### wazuh_indexer_conf_path

#### Default Value

```YAML
wazuh_indexer_conf_path: /etc/wazuh-indexer/
```

### wazuh_indexer_custom_user

#### Default Value

```YAML
wazuh_indexer_custom_user: ''
```

### wazuh_indexer_custom_user_role

#### Default Value

```YAML
wazuh_indexer_custom_user_role: admin
```

### wazuh_indexer_discovery_nodes

#### Default Value

```YAML
wazuh_indexer_discovery_nodes:
  - 127.0.0.1
```

### wazuh_indexer_http_port

#### Default Value

```YAML
wazuh_indexer_http_port: 9200
```

### wazuh_indexer_index_path

#### Default Value

```YAML
wazuh_indexer_index_path: /var/lib/wazuh-indexer/
```

### wazuh_indexer_jvm_xms

#### Default Value

```YAML
wazuh_indexer_jvm_xms:
```

### wazuh_indexer_network_host

#### Default Value

```YAML
wazuh_indexer_network_host: 0.0.0.0
```

### wazuh_indexer_node_data

#### Default Value

```YAML
wazuh_indexer_node_data: true
```

### wazuh_indexer_node_ingest

#### Default Value

```YAML
wazuh_indexer_node_ingest: true
```

### wazuh_indexer_node_master

#### Default Value

```YAML
wazuh_indexer_node_master: true
```

### wazuh_indexer_node_name

#### Default Value

```YAML
wazuh_indexer_node_name: node-1
```

### wazuh_indexer_nolog_sensible

#### Default Value

```YAML
wazuh_indexer_nolog_sensible: true
```

### wazuh_indexer_sec_plugin_conf_path

#### Default Value

```YAML
wazuh_indexer_sec_plugin_conf_path: /usr/share/wazuh-indexer/plugins/opensearch-security/securityconfig
```

### wazuh_indexer_sec_plugin_tools_path

#### Default Value

```YAML
wazuh_indexer_sec_plugin_tools_path: /usr/share/wazuh-indexer/plugins/opensearch-security/tools
```

### wazuh_indexer_start_timeout

#### Default Value

```YAML
wazuh_indexer_start_timeout: 90
```

### wazuh_indexer_version

#### Default Value

```YAML
wazuh_indexer_version: 4.3.9
```

### wazuh_local_certs_path

#### Default Value

```YAML
wazuh_local_certs_path: '{{ playbook_dir }}/files/indexer/certificates'
```

### wazuh_minimum_master_nodes

#### Default Value

```YAML
wazuh_minimum_master_nodes: 2
```

### wazuh_perform_installation

#### Default Value

```YAML
wazuh_perform_installation: true
```

### wazuh_single_node

#### Default Value

```YAML
wazuh_single_node: false
```

## Discovered Tags

**_configure_**

**_debug_**

**_generate-certs_**

**_install_**

**_security_**


## Dependencies

None.

## License

license (GPLv3)

# Copyright

WAZUH Copyright (C) 2016, Wazuh Inc.

## Author

Wazuh


### Based on previous work from dj-wasabi

- https://github.com/dj-wasabi/ansible-ossec-server

### Modified by Wazuh

The playbooks have been modified by Wazuh, including some specific requirements, templates and configuration to improve integration with Wazuh ecosystem.
