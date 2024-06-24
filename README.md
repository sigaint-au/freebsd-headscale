# headscale-openbsd

Install and configure Sigaint headscale and relayd with a self signed certificate.

* IPv6 Only
* Self signed certificate for use with upstream load balancer.

## Requirements

* Headscale 0.22.3
* Ansible
* ipv6 on `vio0` interface
* OpenBSD 7.5 Current

Update `oidc` configuration in `config/secrets.yaml`

## Installation

1. Run the following command to install and configure.

```
ansible-playbook install.yaml --ask-vault-pass
```

2. Update PF with the following lines.
```
pass in on egress inet6 proto tcp to egress port { 80, 443 }
```

