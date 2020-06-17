# Ansible Role: Install FPM - packaging made simple

[![License][license-image]][license-url] [![Ansible Galaxy][ansible-galaxy-image]][ansible-galaxy-url] [![CircleCI][circleci-image]][circleci-url]

Install [FPM](https://fpm.readthedocs.io/en/latest/) for Linux.

## Work on

```yaml
  platforms:
    - name: Fedora
      versions:
        - 31
        - 32
    - name: Ubuntu
      versions:
        - trusty
        - xenial
        - bionic
    - name: Debian
      version:
        - oldstable
        - stable
    - name: EL (CentOS)
      versions:
        # - 7
        - 8
    - name: opensuse
      vesrion:
        - tumbleweed
        - 15.1
    # - name: ArchLinux
    #   version:
    #     - any
```

## Requirements

None.

## Role Variables

None.

## Dependencies

None.

## Example Playbook

Install `latest` FPM on Linux:

`install-fpm.yml`:

```yaml
- name: Install FPM
  hosts: all
  strategy: free
  serial:
    - "100%"
  roles:
    - ansible-role-install-fpm
  tasks:
```

Install FPM `v1.10.0` on Linux:

`install-fpm.yml`:

```yaml
- name: Install FPM
  hosts: all
  strategy: free
  serial:
    - "100%"
  roles:
    - ansible-role-install-fpm
  vars:
    fpm_version: 1.10.0
  tasks:
```

## License

Apache License, Version 2.0

## Author Information

[don Rumata](https://github.com/don-rumata)

## TODO

- ~~Add tests.~~
- Add more tests.
- Add ArchLinux support.

[license-image]: https://img.shields.io/github/license/don-rumata/ansible-role-install-fpm.svg
[license-url]: https://opensource.org/licenses/Apache-2.0

[ansible-galaxy-image]: https://img.shields.io/badge/ansible_galaxy-don__rumata.ansible__role__install__fpm-blue.svg
[ansible-galaxy-url]: https://galaxy.ansible.com/don_rumata/ansible_role_install_fpm

[circleci-image]: https://circleci.com/gh/don-rumata/ansible-role-install-fpm.svg?style=shield
[circleci-url]: https://circleci.com/gh/don-rumata/ansible-role-install-fpm
