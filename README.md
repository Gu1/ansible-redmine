Role Name
=========

Install or Upgrade redmine

Requirements
------------

To Install:
- ANXS.mysql

Role Variables
--------------

To install set up this:

	mysql_port: 3306
	mysql_bind_addres: "0.0.0.0"
	mysql_root_password: "dificil"

	db_host: "127.0.0.1"
	db_name: "redmine"
	db_username: "admin"
	db_password: "unaContrasenia"


You also have the option to configure these:

	redmine_domain: "name.domain"
	redmine_files: "{{ redmine_path }}/files"
	redmine_lang: "es"
	redmine_path: "/opt/redmine"
	redmine_proxy: "/etc/nginx/conf.d/redmine_proxy"
	redmine_public: "{{ redmine_path }}/public"
	redmine_version: "2.5.2"
	target_dump: "/opt/redmine.sql.bz2"
	target_files: "/opt/redmine.tar.bz2"

update: Put this true if you have and old version of redmine
nginx: Put this true if you have nginx installed

Dependencies
------------

This role is for install mysql and you must configure this vars 

- ANXS.mysql

		mysql_port: 3306
		mysql_bind_addres: "0.0.0.0"
		mysql_root_password: "dificil"

Example Playbook
----------------

https://gist.github.com/adeb2e0c32720528cfc6

	---
	- name: Install version 2.5.2
	  hosts: Ansible
	  roles:
	  - { role: redmine, mysql_root_password: "dificil", db_host: "127.0.0.1", db_name: "redmine", db_username: "admin", db_password: "unaContrasenia", redmine_version: "2.5.2" }

	- name: Install version 2.5.2
      hosts: Ansible
      roles:
      - { role: redmine, redmine_version: "2.5.2" }


https://gist.github.com/fc4bebdddf4a2813afdf

	---
	- name: Update to last version
	  hosts: Ansible
	  roles:
    - { role: redmine,  update: true, db_name: "redmine", db_username: "admin", db_password: "unaContrasenia"}


License
-------

GPLv3

Author Information
------------------

Comments are welcome
