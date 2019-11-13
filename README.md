*Read this in other languages: [Russian](README.ru.md)*

HOMER5 + Kamailio
=================

Install HOMER5 + Kamailio (as HEP collector) according to this [manual](https://github.com/sipcapture/homer/wiki/Quick-Install#-manual-setup-from-source-advanced)

Installation
------------

    $ sudo git clone https://github.com/islander/ansible-homer5-kamailio /etc/ansible/roles/homer5-kamailio

Supported platforms
-------------------

[x] `CentOS 7`
[ ] `Debian`
[ ] `Ubuntu`

Role Variables
--------------

See `defaults/main.yml` and distribution-specific configs in `vars/`.

 - `nginx_config` - nginx site config
 - `homer_webroot` - www directory
 - `homer_database_user` - HOMER MySQL user
 - `homer_database_pass` - HOMER MySQL password
 - `homer_api_version` - HOMER API release version
 - `homer_ui_version` - HOMER UI release version

Dependencies
------------

 - [EPEL](https://fedoraproject.org/wiki/EPEL) for CentOS installation.
 - Any MySQL and Nginx roles. Add them to `meta/main.yml`.
 - `vagrant-libvirt` for testing.

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: homer5-kamailio }

Testing
-------

[molecule](https://molecule.readthedocs.io/en/stable/) testing required `vagrant-libvirt` plugin.

Example installation (Ubuntu):

        $ sudo apt install libvirt-dev
        $ vagrant plugin install vagrant-libvirt
        $ vagrant plugin list
        vagrant-libvirt (0.0.45, global)

License
-------

BSD

Author Information
------------------

kiba <zombie32@gmail.com>
