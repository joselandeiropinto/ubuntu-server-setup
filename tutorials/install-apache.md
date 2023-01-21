# Install Apache WebServer
___

- To install Apache
    `sudo apt install apache2`
- Configure firewall to open HTTP and HTTPS ports
    `sudo ufw allow 80/tcp | sudo ufw allow 443/tcp` or you can directly allow the Apache apps through `sudo ufw allow "Apache" | sudo ufw allow "Apache Full" | sudo ufw allow "Apache Secure"`
    * Reload firewall `sudo ufw reload`
- Configure default virtual hosts
    * Open the `/etc/apache/sites-available/default-000.conf` file with your prefered text editor
    * On the `<VirtualHost>` directive add the configuration
        * Add your domain name `ServerName example.com`
        * Add a server alias `ServerAlias www.example.com`
        * Create a `<Directory>` directive to allow .htaccess files on:
    
        ````
            <Directory "{document_root}">
                Allow from all
                AllowOverride All
                Required granted all
            </Directory>
        ````
    - Do the same on the `/etc/apache/sites-available/default-000-le-ssl.conf` file
- Enable headers module
    `sudo a2enmod headers`
- Enable Rewrite module
    `sudo a2enmod rewrite`
- Restart apache.service
    `sudo systemctl restart apache2`