Role Name
=========

This role creates containers of apache2, phpmyadmin, mariadb-server and wordpress and links them. Accessing localhost leads you to the Wordpress initialization page.

Requirements
------------

Docker must be enabled/installed on the machines where this role is called.
Presence of one of those services on the host machine can lead to incompatibilies if the ports are already in use.
In this case, either delete the services already present or change the ports used by the containers (see below)

Role Variables
--------------

Variables set by default are :
- repertoire_projet: /opt  | The (shared) directory where wordpress will be downloaded and unarchived
- database: wordpress      | The database to link to MariaDB
- user: wordpress          | The user that has access to the database MariaDB
- password: wordpress      | The password used to connect to it
- apache: 81               | Apache port by default
- mariadb: 3306	           | MariaDB port by default
- phpmyadmin: 8080         | Phpmyadmin port by default

They can be overloaded by editing the /vars/main.yml file this way:

variable: new_value

Dependencies
------------

No dependencies.

Example Playbook
----------------

- hosts: servers
    roles:
      - lamp_compose

License
-------

BSD

Author Information
------------------

This role was delivered to you by Damien NEVALDO, provider of computer shimagagins since recently actually.
Contact : damien.nevaldo@gmail.com
