#Install

- Install Ansible on your local machine `sudo pip install ansible` (note: brew install doesn't work at the moment)
- Clone repo to folder of choice.
- Run `ansible-galaxy install -r provisioning/requirements.txt --force`
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
See `provisioning/vars/example.yml`

#xdebug Setup
xdebug is installed but not configured correctly.

`sudo cp /etc/php5/mods-available/xdebug.ini /etc/php5/mods-available/`

Edit xdebug.ini to enable remote debugging then restart php5-fpm.
