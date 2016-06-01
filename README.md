Teampass
=========

This role is intended to allow an easy installation of Teampass.

Requirements
------------

None

Role Variables
--------------

You need to setup the next variables:
 - teampass_db
 - teampass_db_user
 - teampass_db_password
 - teampass_server_name

Dependencies
------------

- geerlingguy.apache-php-fpm
- geerlingguy.mysql

Example Playbook
----------------

   - hosts: servers
      vars_files:
        vars/main.yml
      roles:
         - { role: kporras07.teampass }

Inside _vars/main.yml_:

    - teampass_db: "teampass_db"
    - teampass_db_user: "teampass_user"
    - teampass_db_password: "teampass"
    - teampass_server_name: "teampass.mycompany.com"

Besides that, you need to ensure to have the next configuration for geerlinguy.php role:

```
php_memory_limit: "128M"
php_max_execution_time: "120"
php_packages:
  - php5.6
  - php5.6-cli
  - php5.6-common
  - php5.6-mysql
  - php5.6-mcrypt
  - php5.6-json
  - php5.6-gd
  - php5.6-mbstring
  - php5.6-xml
  - php5.6-bcmath
  - php-mysqlnd-ms
php_conf_paths:
  - /etc/php/5.6/apache2
  - /etc/php/5.6/cli
```

License
-------

MIT/BSD

Author Information
------------------

This role was created in 2016 by @kporras07.
