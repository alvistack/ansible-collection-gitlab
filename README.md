# Ansible Collection for GitLab

<a href="https://alvistack.com" title="AlviStack" target="_blank"><img src="/alvistack.svg" height="75" alt="AlviStack"></a>

[![Gitlab pipeline
status](https://img.shields.io/gitlab/pipeline/alvistack/ansible-collection-gitlab/master)](https://gitlab.com/alvistack/ansible-collection-gitlab/-/pipelines)
[![GitHub
tag](https://img.shields.io/github/tag/alvistack/ansible-collection-gitlab.svg)](https://github.com/alvistack/ansible-collection-gitlab/tags)
[![GitHub
license](https://img.shields.io/github/license/alvistack/ansible-collection-gitlab.svg)](https://github.com/alvistack/ansible-collection-gitlab/blob/master/LICENSE)
[![Ansible
Collection](https://img.shields.io/badge/galaxy-alvistack.gitlab-blue.svg)](https://galaxy.ansible.com/alvistack/gitlab)

Ansible collection for deploying GitLab.

This Ansible collection provides Ansible playbooks and roles for the
deployment and configuration of an [GitLab](https://www.gitlab.org/)
environment.

## Requirements

This collection require Ansible community package 4.10 or higher.

This collection was designed for:

-   Ubuntu 20.04, 22.04, 23.10, 24.04
-   AlmaLinux 8, 9
-   openSUSE Leap 15.5, Tumbleweed
-   Debian 11, 12, Testing
-   Fedora 38, 39, Rawhide
-   CentOS 7, 8 Stream, 9 Stream
-   RHEL 7, 8, 9

## Quick Start

### Bootstrap Ansible and Roles

Start by cloning the repository, checkout the corresponding branch, and
init with `git submodule`, then install Ansible (see
<https://software.opensuse.org/download/package?package=ansible&project=home%3Aalvistack>):

    # GIT checkout development branch
    mkdir -p /opt/ansible-collection-gitlab
    cd /opt/ansible-collection-gitlab
    git init
    git remote add upstream https://github.com/alvistack/ansible-collection-gitlab.git
    git fetch --all --prune
    git checkout upstream/develop -- .
    git submodule sync --recursive
    git submodule update --init --recursive

    # Bootstrap Ansible
    echo 'deb http://downloadcontent.opensuse.org/repositories/home:/alvistack/xUbuntu_22.04/ /' | tee /etc/apt/sources.list.d/home:alvistack.list
    curl -fsSL https://downloadcontent.opensuse.org/repositories/home:alvistack/xUbuntu_22.04/Release.key | gpg --dearmor | tee /etc/apt/trusted.gpg.d/home_alvistack.gpg > /dev/null
    apt update
    apt install ansible

    # Confirm the version of Ansible
    ansible --version

### AIO

All-in-one (AIO) build is a great way to perform an GitLab build for:

-   A development environment
-   An overview of how all the GitLab services fit together
-   A simple lab deployment

Simply execule our default Molecule test case and it will deploy all
default components into your localhost:

    # Run Molecule test case
    molecule test -s default

### Molecule

You could also run our
[Molecule](https://molecule.readthedocs.io/en/stable/) test cases if you
have [Vagrant](https://www.vagrantup.com/) and
[Libvirt](https://libvirt.org/) installed, e.g.

    # Run Molecule on Ubuntu 22.04
    molecule converge -s ubuntu-22.04

Please refer to [.gitlab-ci.yml](.gitlab-ci.yml) for more information on
running Molecule.

## Versioning

### `YYYYMMDD.Y.Z`

Release tags could be find from [GitHub
Release](https://github.com/alvistack/ansible-collection-gitlab/tags) of
this repository. Thus using these tags will ensure you are running the
most up to date stable version of this image.

### `YYYYMMDD.0.0`

Version tags ended with `.0.0` are rolling release rebuild by [GitLab
pipeline](https://gitlab.com/alvistack/ansible-collection-gitlab/-/pipelines)
in weekly basis. Thus using these tags will ensure you are running the
latest packages provided by the base image project.

## License

-   Code released under [Apache License 2.0](LICENSE)
-   Docs released under [CC BY
    4.0](http://creativecommons.org/licenses/by/4.0/)

## Author Information

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>
