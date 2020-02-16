Ansible Role: Install Nextcloud and Collabora Office using Docker
=========

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

Ahmad Haghighi. (ahmadhaghighi.com)
