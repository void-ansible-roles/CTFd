CTFd
====

Installs CTFd on Void Linux and serves it using nginx and uWSGI.

Requirements
------------
Requires the PostgreSQL and nginx ansible roles from 
[void-ansible-roles](https://github.com/void-ansible-roles)

Role Variables
--------------

Required:

	ctfd_site_url: the url you will serve the site at
	ctfd_dbpass: the password for the database

Optional:

	ctfd_db: the name of the PostgreSQL database to be used
	ctfd_dbuser: the name of the user to use the database
	ctfd_email: the email address of the site administrator
	ctfd_deploy_directory: the directory CTFd will be installed
	ctfd_serve_directory: the directory CTFd will serve from
	
