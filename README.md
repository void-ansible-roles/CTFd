CTFd
====


What is does this role do?
--------------------------

Installs CTFd on Void Linux and serves it using nginx and uWSGI. Also creates 
the /etc/nginx/site-available/ctfd/ directory where locations not managed by 
CTFd can be put. WARNING: These locations may conflict with locations CTFd 
manages. It is up to the administrator to ensure this does not happen.


Meta
----

Files Managed:
  * /etc/iptables.d/ctfd.rules
  * /etc/sv/ctfd/run
  * /etc/nginx/locations.d/ctfd
  * /etc/nginx/sites-available/ctfd.conf
  * /etc/nginx/sites-enabled/ctfd.conf
  * /var/service/ctfd
  * /opt/ctfd
  * /srv/ctfd

Defaults Provided:
  * ctfd_db: ctfdb
  * ctfd_dbuser: ctfddbuser
  * ctfd_site_url: .ctfd.io
  * ctfd_site_mount: /
  * ctfd_email: noreply@ctfd.io
  * ctfd_deploy_directory: /opt/ctfd
  * ctfd_serve_directory: /srv/ctfd
  * ctfd_commit_hash: 01cb189

Variables Required:
  * ctfd_site_url: the url you will serve the site at
  * ctfd_dbpass: the password for the database

Optional Variables:
  * ctfd_db: the name of the PostgreSQL database to be used
  * ctfd_dbuser: the name of the user to use the database
  * ctfd_email: the email address of the site administrator
  * ctfd_deploy_directory: the directory CTFd will be installed
  * ctfd_serve_directory: the directory CTFd will serve from
  * ctfd_commit_hash: the last known good commit for CTFd
	
Files Required:
  * None

Optional Files:
  * None

Conflicting Roles:
  * None

Depends On:
  * [PostgreSQL](https://github.com/void-ansible-roles/PostgreSQL)
  * [nginx](https://github.com/void-ansible-roles/nginx)
