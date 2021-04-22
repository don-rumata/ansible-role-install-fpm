# Ansible Role: Install FPM - packaging made simple

[![License][license-image]][license-url] [![Ansible Galaxy][ansible-galaxy-image]][ansible-galaxy-url] [![CircleCI][circleci-image]][circleci-url] [![Ansible Galaxy Quality][ansible-galaxy-quality-image]][ansible-galaxy-url]

Install [FPM](https://fpm.readthedocs.io/en/latest/) for Linux.

## Work on

```yaml
  platforms:
    - name: Fedora
      versions:
        - 33
    - name: Ubuntu
      versions:
        - xenial
        - bionic
        - focal
    - name: Debian
      version:
        - oldstable
        - stable
    - name: EL (CentOS)
      versions:
        - 8
    - name: opensuse
      vesrion:
        - tumbleweed
        - 15.2
    # - name: ArchLinux
    #   version:
    #     - any
```

## Requirements

None.

## Role Variables

```yaml
# "User install" is default, because https://ru.stackoverflow.com/a/907613/191416
# fpm_method_install: system
fpm_method_install: user

# fpm_docs_install: no
fpm_docs_install: yes

# By default, the latest version from https://rubygems.org/gems/fpm is installed.
# fpm_version: x.y.z
```

## Dependencies

None.

## Example Playbooks

Install `latest` FPM with help files in `~/.gem` on Linux:

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

Install FPM `v1.10.0` **without** help files on Linux:

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
    fpm_docs_install: no
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

[ansible-galaxy-quality-image]: https://img.shields.io/ansible/quality/49352
