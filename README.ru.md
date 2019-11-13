HOMER5 + Kamailio
=================

Установка HOMER5 + Kamailio (в качестве HEP-коллектора) по данной [инструкции](https://github.com/sipcapture/homer/wiki/Quick-Install#-manual-setup-from-source-advanced)

Установка
----------

    $ sudo git clone https://github.com/islander/ansible-homer5-kamailio /etc/ansible/roles/homer5-kamailio

Поддерживаемые платформы
------------------------

[x] `CentOS 7`
[ ] `Debian`
[ ] `Ubuntu`

Переменные роли
---------------

Смотри `defaults/main.yml` и дистрибутиво-зависимые конфигурации в `vars/`:

 - `nginx_config` - nginx site config
 - `homer_webroot` - www directory
 - `homer_database_user` - HOMER MySQL user
 - `homer_database_pass` - HOMER MySQL password
 - `homer_api_version` - HOMER API release version
 - `homer_ui_version` - HOMER UI release version

Зависимости
-----------

 - [EPEL](https://fedoraproject.org/wiki/EPEL) для CentOS.
 - Любые роли для MySQL и Nginx. Прописываются в `meta/main.yml`.
 - `vagrant-libvirt` для тестирования.

Пример плейбука
---------------

    - hosts: servers
      roles:
         - { role: homer5-kamailio }

Тестирование
------------

Для тестирования с помощью [molecule](https://molecule.readthedocs.io/en/stable/) требуется плагин `vagrant-libvirt`.

Пример установки (Ubuntu):

        $ sudo apt install libvirt-dev
        $ vagrant plugin install vagrant-libvirt
        $ vagrant plugin list
        vagrant-libvirt (0.0.45, global)

Лицензия
--------

BSD

Автор
-----

kiba <zombie32@gmail.com>
