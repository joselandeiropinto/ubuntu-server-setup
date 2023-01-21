# Configure Firewall 
___

To configure firewall rules use the `ufw` command-line utility, which comes installed with the distribution.

- List all rules
    `sudo ufw status` or `sudo ufw status verbose`
- Start by list all apps available
    `sudo ufw app list`
- To enable an registered app
    `sudo ufw allow "APP_NAME"` ie. `sudo ufw allow "OpenSSH"`
- To enable specific port 
    `sudo ufw allow PORT/PROTOCOL` ie. `sudo ufw allow 21/tcp`
- To enable specific port to a specific ip address
    `sudo allow/deny from IP_ADDRESS to PORT/PROTOCOL` ie. `sudo ufw allow from 198.1.1.23 to 5000/tcp`
- To enable/deny specific port to a ip subnet
    `sudo allow/deny from IP_ADDRESS/SUBNET to PORT/PROTOCOL` ie. `sudo ufw deny from 198.1.1.23/24 to 5000/tcp`
- To disable an enabled rule
    `sudo ufw delete RULE` ie. `sudo ufw delete allow 22/tcp`
- To enable the firewall 
    `sudo ufw enable`
- To disable the firewall 
    `sudo ufw disable`
- To apply new rules when firewall is already enabled
    `sudo ufw reload`
        
