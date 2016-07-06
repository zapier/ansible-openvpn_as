openvpn_as
==========

[![Build Status](https://travis-ci.org/kbrebanov/ansible-openvpn_as.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-openvpn_as)

Installs and configures OpenVPN Access Server

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                                       | Default                                                                                                                                             | Description                                 |
|:-------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------|:--------------------------------------------|
| openvpn_as_version                         | 2.1.1                                                                                                                                               | Version of OpenVPN Access Server to install |
| openvpn_as_sha256sum                       | c35263b8996bf596708c91010cfdc76e87e3555cb8cf16f0c375604290ee9191                                                                                    | SHA 256 sum of package                      |
| openvpn_as_password                        | $6$j8B0A1aiU$53BF5A6qO74IDJWTDqgaafnBar1c.LOKK7sdBxwXJY/K/I/XUFAWNsfm78dI9YBDPTHJlmaZoE.QFg.3DEobO1 (openvpn)                                       | Password for openvpn admin user             |
| openvpn_as_admin_ui_https_ip_address       | eth0                                                                                                                                                |                                             |
| openvpn_as_admin_ui_https_port             | 943                                                                                                                                                 |                                             |
| openvpn_as_auth_module_type                | pam                                                                                                                                                 |                                             |
| openvpn_as_cs_cws_proto_v2                 | true                                                                                                                                                |                                             |
| openvpn_as_cs_https_ip_address             | eth0                                                                                                                                                |                                             |
| openvpn_as_cs_https_port                   | 943                                                                                                                                                 |                                             |
| openvpn_as_cs_prof_sign_web                | true                                                                                                                                                |                                             |
| openvpn_as_cs_ssl_method                   | SSLv3                                                                                                                                               |                                             |
| openvpn_as_cs_tls_version_min              | 1.0                                                                                                                                                 |                                             |
| openvpn_as_host_name                       | "{{ ansible_eth0.ipv4.address }}"                                                                                                                   |                                             |
| openvpn_as_vpn_client_routing_inter_client | false                                                                                                                                               |                                             |
| openvpn_as_vpn_client_routing_reroute_dns  | false                                                                                                                                               |                                             |
| openvpn_as_vpn_client_routing_reroute_gw   | false                                                                                                                                               |                                             |
| openvpn_as_vpn_daemons                     | [{client_netmask_bits: 20, client_network: 172.27.224.0, listen_ip_address: eth0, listen_port: 443, listen_protocol: tcp, server_ip_address: eth0}] |                                             |
| openvpn_as_server_daemon_enable            | true                                                                                                                                                |                                             |
| openvpn_as_server_daemon_tcp_port          | 943                                                                                                                                                 |                                             |
| openvpn_as_server_daemon_udp_port          | 1194                                                                                                                                                |                                             |
| openvpn_as_server_routing_private_network  | nat                                                                                                                                                 |                                             |

Dependencies
------------

None

Example Playbook
----------------


Install OpenVPN Access Server
```yaml
- hosts: all
  roles:
    - kbrebanov.openvpn_as
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov