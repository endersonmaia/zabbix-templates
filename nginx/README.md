# nginx

Template and script to monitor nginx web server.

## Items

  - Nginx Waiting
  - Nginx Writing
  - Nginx Requests
  - Nginx Reading
  - Nginx Active
  - Nginx Handled
  - Nginx Accepted

## Requirements

You need to have `wget` installed.

I'm using Ubuntu, and some steps will be different if you use a different Linux distribution.

## Configuring

### nginx

  - Copy the `nginx-status.conf` file to the `/etc/nginx/sites-available` directory
  - Edit the file to add your zabbix server IP to the `allow` config option;
  - Enable this configuration linking it to `sites-enabled` using this command `# ln -s /etc/sites-available/nginx-status.conf /etc/sites-enabled/nginx-status.conf`
  - Restart the nginx service with the `# service nginx restart` command

Test the access to the status site at http://localhost:55777/nginx-status.

### zabbix-agent

  - Copy the file `userparameter_nginx.conf` to the `/etc/zabbix/zabbix_agent.d/` directory
  - Verify that you have na `/etc/zabbix/zabbix_agent.d/` directive in you `zabbix-agentd.conf` file
  - Restart the `zabbix-agentd` service with the  `# service zabbix-agentd restart` command
  
### Template

Download and import the file `Template_App_nginx.zbx.xml` and import it using the Zabbix Web Frontend, and then enable it in the host you configured for monitoring nginx.

## Credits

Based on this : http://www.foscode.com/monitor-phpfpm-nginx-zabbix/.