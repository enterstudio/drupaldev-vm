#Install [![Build Status](https://travis-ci.org/mikebell/drupaldev-vm.svg?branch=master)](https://travis-ci.org/mikebell/drupaldev-vm)

- Install Ansible on your local machine `sudo pip install ansible` (note: Ansible 1.8+ required)
- Clone repo to folder of choice.
- Run `sudo ansible-galaxy install -r provisioning/requirements.txt --force`
- Run `mkdir sites`
- Run `vagrant plugin install vagrant-cachier` (optional)

#Includes
- PHP 5.5
- Mariadb
- Solr 4.x
- Nginx

#SSH Forwarding

1. Add the following to your .ssh/config:

    `Host 33.33.33.10`

    `AgentForward yes`

2. Run `ssh-add`
3. To test `vagrant ssh` then `ssh -T git@github.com`

#vhost Config
1. Run `cp example.yml sites.yml`
2. Amend the file sites.yml to rename your local environment as required. The server_name must end in .drupal.dev for you to be able to access you local site through the browser.
3. Update your database settings as required: replace `database_name` with the name of the database you wish to be created, and `db_user` and `db_pass` with the username and password of the MySQL user account your local site should use.

See `provisioning/vars/example.yml`

#xdebug Setup
xdebug is installed but not configured correctly.

`sudo mv /etc/php5/conf.d/xdebug.ini /etc/php5/fpm/conf.d/`

Edit xdebug.ini to enable remote debugging then restart php5-fpm.
