# Ansible Collection for Gnome

[![Travis](https://img.shields.io/travis/com/alvistack/ansible-collection-gnome.svg)](https://travis-ci.com/alvistack/ansible-collection-gnome)
[![GitHub release](https://img.shields.io/github/release/alvistack/ansible-collection-gnome.svg)](https://github.com/alvistack/ansible-collection-gnome/releases)
[![GitHub license](https://img.shields.io/github/license/alvistack/ansible-collection-gnome.svg)](https://github.com/alvistack/ansible-collection-gnome/blob/master/LICENSE)
[![Ansible Collection](https://img.shields.io/badge/galaxy-alvistack.gnome-blue.svg)](https://galaxy.ansible.com/alvistack/gnome)

Ansible collection for deploying Gnome.

This Ansible collection provides Ansible playbooks and roles for the deployment and configuration of an [Gnome](https://www.gnome.org/) environment.

## Requirements

This collection require Ansible 2.10 or higher.

This collection was designed for:

  - Ubuntu 18.04/20.04/20.10
  - RHEL/CentOS 7/8
  - openSUSE Leap 15.2
  - Debian 10
  - Fedora 33

## Quick Start

### Bootstrap Ansible and Roles

Start by cloning the repository, checkout the corresponding branch, and init with `git submodule`, then bootstrap Python3 + Ansible with provided helper script:

    # GIT clone the development branch
    git clone --branch develop https://github.com/alvistack/ansible-collection-gnome
    cd ansible-collection-gnome
    
    # Setup Roles with GIT submodule
    git submodule init
    git submodule sync
    git submodule update
    
    # Bootstrap Ansible
    ./scripts/bootstrap-ansible.sh
    
    # Confirm the version of Python3, PIP3 and Ansible
    python3 --version
    pip3 --version
    ansible --version

### AIO

All-in-one (AIO) build is a great way to perform an Gnome build for:

  - A development environment
  - An overview of how all the Gnome services fit together
  - A simple lab deployment

Simply execule our default Molecule test case and it will deploy all default components into your localhost:

    # Run Molecule test case
    molecule test -s default

### Molecule

You could also run our [Molecule](https://molecule.readthedocs.io/en/stable/) test cases if you have [Vagrant](https://www.vagrantup.com/) and [Libvirt](https://libvirt.org/) installed, e.g.

    # Bootstrap Vagrant and Libvirt
    ./scripts/bootstrap-vagrant.sh
    
    # Run Molecule on Ubuntu 20.04
    molecule converge -s ubuntu-20.04

Please refer to [.travis.yml](.travis.yml) for more information on running Molecule.

## License

  - Code released under [Apache License 2.0](LICENSE)
  - Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

  - Wong Hoi Sing Edison
      - <https://twitter.com/hswong3i>
      - <https://github.com/hswong3i>
