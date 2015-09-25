```bash
cd /etc/apache2/sites-available/
sudo cp 000-default.conf virtual_host.local.conf
sudo nano virtual_host.local.conf
```

Edit virtual_host.local.conf file like this:
```html
<VirtualHost virtual_host.local:80>
    DocumentRoot /home/user/public_html
    ServerName virtual_host.local
    
    <Directory /home/user/public_html>
        # AllowOverride All      # Deprecated
        # Order Allow,Deny       # Deprecated
        # Allow from all         # Deprecated

        # --New way of doing it
        Require all granted    
    </Directory>
    .
    .
    .
</VirtualHost>
```

Enable and add virtualhost to hosts
```bash
sudo a2ensite virtual_host.local.conf
sudo nano /etc/hosts
sudo a2enmod rewrite
sudo service apache2 restart
```
