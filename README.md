Role Name
=========

Install or Upgrade redmine

Requirements
------------

To Install:
- ANXS.postgresql

Role Variables
--------------

To install set up this:

    redmine_db_host: ''
    redmine_db_name: redmine
    redmine_db_username: redmine

You also have the option to configure these:

	redmine_files: "{{ redmine_path }}/files"
	redmine_lang: "es"
	redmine_path: "/opt/redmine"
	redmine_public: "{{ redmine_path }}/public"
	redmine_version: "2.5.3"

redmine_update: Put this true if you have and old version of redmine

Dependencies
------------

ANXS.postgresql with peer authentication enabled

License
-------

GPLv3

Author Information
------------------

Comments are welcome
