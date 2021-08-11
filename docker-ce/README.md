Role Name
=========

This role does some things (change this sentence, obviously...)

Requirements
------------

None.

Role Variables
--------------

Set the following variables via a mechanism like `host_vars/(hostname)`, your playbook, or the ansible command line:
* variable(s)

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:
```
    - hosts: groupNames
      roles:
         - role: docker-ce  # or renamed role via requirements.yml
           # any other variables can go here
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
