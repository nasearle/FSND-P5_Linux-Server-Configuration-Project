## Linux Server Configuration Project
IP Address: 52.27.14.228

SSH Port: 2200

URL: [http://52.27.14.228](http://52.27.14.228) 

An installation of Ubuntu Linux on a virtual machine to host a Flask web application.
The Linux server is configured to install updates automatically, ban potential 
attackers, and has monitoring software installed.

### Using the Application:
Go to the URL above in a webbrowser. Log in (button at the top right 
corner of the front page) with either a Google+ or Facebook account to create 
and edit Restaurants and Menu Items. By default, the first account you log in
with will be able to edit the sample restaurants and menu items. After this 
initial login, only the creator of a restaurant will be able to edit it.

### Installed Software and Configuration Changes on Linux Server:
1. Created .ssh directory in root home and added public key to authorized_keys file in .ssh
2. Added user 'grader' and granted it permission to sudo
3. Updated installed packages
4. Changed the SSH port from 22 to 2200 in /etc/ssh/sshd_config
5. Disallowed login as root and allowed login as grader
6. Configured the local timezone to UTC with `$ dpkg-reconfigure tzdata`
7. Configured the firewall to allow ports 2200, 80 and 123
8. Installed Apache and configured it to serve a mod_wsgi application
9. Installed Git
10. Installed and enabled mod_wsgi
11. Created directory /var/www/catalog/catalog for the Flask app
12. Installed virtualenv and gave it full permissions
13. Installed Flask
14. Configured and enabled a new virtual host by editing /etc/apache2/sites-available/catalog.conf
15. Created the wsgi file in /var/www/catalog and restarted Apache
16. Cloned P3 GitHub repository and placed files in /var/www/catalog/catalog
17. Made the Git repository inaccessible with .htaccess file 
18. Installed packages: httplib2, requests, oauth2client, sqlalchemy, python-psycopg2
19. Installed PostgreSQL and configured the catalog app to connect to it
20. Added user 'catalog' in linux and psql and gave it permission to create tables
21. Created a database 'catalog' with owner 'catalog'
22. Added server hostname to /etc/apache2/sites-available/catalog.conf	
	
### Additional Functionality:
1. Installed fail2ban and configured it to ban a potential attacker for
	10 minutes after 3 unsuccessful login attempts are made within a 10-minute window.
2. Included scripts to automatically manage package updates with `$ sudo apt-get install unattended-upgrades`
and then `$ sudo dpkg-reconfigure unattended-upgrades`
3. Installed Glances and PySensors to monitor application status. Type `$ glances` into
the command line to see the output
	
### Resources:
https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-14-04
https://help.ubuntu.com/community/UFW
https://www.digitalocean.com/community/tutorials/how-to-protect-ssh-with-fail2ban-on-ubuntu-14-04
https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
http://askubuntu.com/questions/293426/system-monitoring-tools-for-ubuntu
https://www.digitalocean.com/community/tutorials/how-to-secure-postgresql-on-an-ubuntu-vps
http://www.postgresql.org/docs/9.1/static/app-createuser.html
http://www.postgresql.org/docs/9.1/static/auth-pg-hba-conf.html
http://killtheyak.com/use-postgresql-with-django-flask/
http://flask.pocoo.org/docs/0.10/config/
http://drumcoder.co.uk/blog/2010/nov/12/apache-environment-variables-and-mod_wsgi/
http://askubuntu.com/questions/293426/system-monitoring-tools-for-ubuntu
https://discussions.udacity.com/t/p5-how-i-got-through-it/15342
https://discussions.udacity.com/t/markedly-underwhelming-and-potentially-wrong-resource-list-for-p5/8587




