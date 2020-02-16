Ansible Role: Install Nextcloud and Collabora Office using Docker
=========

[![Build Status][travis-build-status]][travis-tests] [![Ansible Role][ansible-role-shield]][ansible-role]

This role install Nextcloud and Collabora office on Docker, using Nginx as reverse proxy (currently only for Debian-based OS).

Requirements
------------

### Python2 Packages
* `docker-compose` (`pip install docker-compose`)  
* `docker` (`pip install docker`)  

### Ansible Modules
* docker_compose 
* service 
* file 
* template 

Role Variables
--------------

See `defaults/main.yml` for all available variables. Mandatory variable(s) is checked on the `check_vars.yml` task.

### Mandatory variable(s):
* nextcloud_domain\
* nextcloud_office_domain (if using Collabora office)
* nextcloud_office_white_domains (if using Collabora office)

Example Playbook
----------------

```yml
---
- name: Deploy Nextcloud
  hosts: nextcloud
  roles:
    - {role: nextcloud-docker} 
```

Inside `group_vars/nextcloud`:  
```yml
---
nextcloud_domain: "cloud.example.com"
```

License
-------

AGPLv3

Author Information
------------------

Ahmad Haghighi. (https://ahmadhaghighi.com)


[travis-build-status]: https://api.travis-ci.org/haghighi-ahmad/ansible-role-nextcloud-docker.svg?branch=master&style=flat-square "Travis-CI Build Status"
[travis-tests]: https://travis-ci.org/haghighi-ahmad/ansible-role-nextcloud-docker "Travis-CI Tests"
[ansible-role-shield]: https://img.shields.io/ansible/role/46602.svg?style=flat-square "Nextcloud Docker on Ansible Galaxy"
[ansible-role]: https://galaxy.ansible.com/haghighi_ahmad/nextcloud_docker "Nextcloud Docker on Ansible Galaxy"

