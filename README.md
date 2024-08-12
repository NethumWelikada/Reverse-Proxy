#Setting Up Apache as a Reverse Proxy on Ubuntu**
**Install Apache and Required Modules**

#Update Package List and Install Apache:**
sudo apt update
sudo apt install apache2

#Enable Necessary Apache Modules:**
sudo a2enmod proxy
sudo a2enmod proxy_http
sudo a2enmod ssl  # Only if you need HTTPS

#Configure Apache Virtual Hosts

#Create Configuration for `www.your domain`:**
sudo nano /etc/apache2/sites-available/your domain.conf

#Add the following content:(apache - Replace your domain and IP addresses)

   <VirtualHost *:80>
       ServerName www.your domain
       ProxyPreserveHost On
       ProxyPass / http://Your Static IP:Port/
       ProxyPassReverse / http://Your Static IP:Port/
       ErrorLog ${APACHE_LOG_DIR}/your domain_error.log
       CustomLog ${APACHE_LOG_DIR}/your domain_access.log combined
   </VirtualHost>

#Proxy Server Port Forwarding
80 | 443
