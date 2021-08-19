Role Name
=========

This role installs Docker Community Edition on Ubuntu

Requirements
------------

None.

Role Variables
--------------

Set the following variables via a mechanism like `host_vars/(hostname)`, your playbook, or the ansible command line:
* `docker_prereqs`
* `docker_pkgs`

Dependencies
------------

None.

Example Playbook
----------------

Role/variables spec in playbook:
```
    - hosts: groupNames
      roles:
        - role: docker-ce  # or renamed role via requirements.yml
          # taken verbatim from vars/main.yml; override as needed
          docker_prereqs:
            - apt-transport-https
            - ca-certificates
            - curl
            - gnupg-agent
            - software-properties-common
          docker_pkgs:
            - docker-ce
            - docker-ce-cli
            - containerd.io
```
License
-------

GPL 2.0

Author Information
------------------

No comment.

Installation
------------

As part of a larger playbook, add the following in `requirements.yml` (`name` can be whatever you prefer):
```
- name: docker-ce
  src: git+https://github.com/zer0master/ansible-docker-ce.git
  scm: git
```
Then from the base of your repo, install with
```
ansible-galaxy role install -vvvv --role-file requirements.yml --roles-path roles/
```
This assumes a playbook layout with `roles`, `host/group_vars`, and possibly similar first-level folders.
