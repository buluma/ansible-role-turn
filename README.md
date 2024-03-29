# Ansible role [turn](https://galaxy.ansible.com/ui/standalone/roles/buluma/turn/documentation)

Install and configure a (co) turn server on your system.

|GitHub|Version|Issues|Pull Requests|Downloads|
|------|-------|------|-------------|---------|
|[![github](https://github.com/buluma/ansible-role-turn/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-turn/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-turn.svg)](https://github.com/buluma/ansible-role-turn/releases/)|[![Issues](https://img.shields.io/github/issues/buluma/ansible-role-turn.svg)](https://github.com/buluma/ansible-role-turn/issues/)|[![PullRequests](https://img.shields.io/github/issues-pr-closed-raw/buluma/ansible-role-turn.svg)](https://github.com/buluma/ansible-role-turn/pulls/)|[![Ansible Role](https://img.shields.io/ansible/role/d/buluma/turn)](https://galaxy.ansible.com/ui/standalone/roles/buluma/turn/documentation)|

## [Example Playbook](#example-playbook)

This example is taken from [`molecule/default/converge.yml`](https://github.com/buluma/ansible-role-turn/blob/master/molecule/default/converge.yml) and is tested on each push, pull request and release.

```yaml
---
- name: Converge
  hosts: all
  become: true
  gather_facts: true

  roles:
    - role: buluma.turn
      turn_listening_ip: "0.0.0.0"
      turn_external_ip: "1.2.3.4"
```

The machine needs to be prepared. In CI this is done using [`molecule/default/prepare.yml`](https://github.com/buluma/ansible-role-turn/blob/master/molecule/default/prepare.yml):

```yaml
---
- name: Prepare
  hosts: all
  become: true
  gather_facts: false

  roles:
    - role: buluma.bootstrap
    - role: buluma.epel
```

Also see a [full explanation and example](https://buluma.github.io/how-to-use-these-roles.html) on how to use these roles.

## [Role Variables](#role-variables)

The default values for the variables are set in [`defaults/main.yml`](https://github.com/buluma/ansible-role-turn/blob/master/defaults/main.yml):

```yaml
---
# defaults file for turn

turn_listening_port: 3478
turn_fingerprint: true
turn_lt_cred_mech: false
turn_use_auth_secret: true
turn_static_auth_secret: 96ef8dbed1ba36132d9cccfa608d1f90f879d7fb38cb5c18
turn_realm: nextcloud.meinit.nl
turn_total_quota: 100
turn_bps_quota: 0
turn_stale_nonce: 600
turn_no_loopback_peers: true
turn_no_multicast_peers: true
turn_simple_log: true
turn_cli_password: 5S4QtTbkC2tzJj4jRKePZJlmCVU3ljnG
turn_server_name: "{{ ansible_fqdn }}"
turn_listening_ip: "{{ ansible_default_ipv4.address }}"
turn_external_ip: "{{ ansible_default_ipv4.address }}"
```

## [Requirements](#requirements)

- pip packages listed in [requirements.txt](https://github.com/buluma/ansible-role-turn/blob/master/requirements.txt).

## [State of used roles](#state-of-used-roles)

The following roles are used to prepare a system. You can prepare your system in another way.

| Requirement | GitHub | Version |
|-------------|--------|--------|
|[buluma.bootstrap](https://galaxy.ansible.com/buluma/bootstrap)|[![Ansible Molecule](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-bootstrap/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-bootstrap.svg)](https://github.com/shadowwalker/ansible-role-bootstrap)|
|[buluma.epel](https://galaxy.ansible.com/buluma/epel)|[![Ansible Molecule](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml/badge.svg)](https://github.com/buluma/ansible-role-epel/actions/workflows/molecule.yml)|[![Version](https://img.shields.io/github/release/buluma/ansible-role-epel.svg)](https://github.com/shadowwalker/ansible-role-epel)|

## [Context](#context)

This role is a part of many compatible roles. Have a look at [the documentation of these roles](https://buluma.github.io/) for further information.

Here is an overview of related roles:

![dependencies](https://raw.githubusercontent.com/buluma/ansible-role-turn/png/requirements.png "Dependencies")

## [Compatibility](#compatibility)

This role has been tested on these [container images](https://hub.docker.com/u/buluma):

|container|tags|
|---------|----|
|[EL](https://hub.docker.com/r/buluma/enterpriselinux)|8|
|[Debian](https://hub.docker.com/r/buluma/debian)|all|
|[Fedora](https://hub.docker.com/r/buluma/fedora)|all|
|[Ubuntu](https://hub.docker.com/r/buluma/ubuntu)|bionic|

The minimum version of Ansible required is 2.12, tests have been done to:

- The previous version.
- The current version.
- The development version.

If you find issues, please register them in [GitHub](https://github.com/buluma/ansible-role-turn/issues)

## [Changelog](#changelog)

[Role History](https://github.com/buluma/ansible-role-turn/blob/master/CHANGELOG.md)

## [License](#license)

[Apache-2.0](https://github.com/buluma/ansible-role-turn/blob/master/LICENSE)

## [Author Information](#author-information)

[Shadow Walker](https://buluma.github.io/)
