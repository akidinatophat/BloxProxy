# BloxProxy
BloxProxy is yet another Roblox API Proxy for HttpService with 3 things in mind:
- Simple
- Reliable
- Configurable

With BloxProxy, say goodbye to dealing with Node.JS and NPM, and long live the hassle of Heroku deployments. All you need is to edit, add, and reload.
If you want to add another Roblox API to BloxProxy, just copy and paste the location directive, edit the url, and reload NGINX. It's that easy.

# Current API list
https://api.bloxproxy.site - Main API\n
https://api2.bloxproxy.site - Testing API - unstable\n
Do NOT use these in a production enviroment!

# Prerequisites for installation
You'll need the following to install BloxProxy:
- A Linux machine with a public IP(VPS Recommended)
- A domain name(you can get one at freenom)

# Installation
This tutorial is meant for Ubuntu Server. Installing NGINX is different for every distro.

```
# Update your repos. Optional but recommended.
sudo apt update

# Install the packages
sudo apt install -y nginx certbot

# Verify nginx is installed
nginx -v
# Expected output: nginx version: nginx/1.XX.X

# Assuming you already have an available domain name, go to your registrar's DNS settings, then add an A record which points to your machine's Public IP Address(you can get it by running "curl https://ipv4.myip.wtf/text").

# Stop NGINX service for now
sudo systemctl stop nginx
sudo pkill nginx

# Get an SSL Certificate
sudo certbot certonly --standalone -d <your domain>

# Ensure you enter a valid email for urgent notifications about your certificate.

# After certbot gives you your certificate, clone the repo
git clone https://github.com/akidinatophat/BloxProxy.git

# Copy snippets folder
sudo cp -r ./BloxProxy/snippets/ /etc/nginx/

# Edit nginx.conf
sudo nano /etc/nginx/nginx.conf
# Add the following line at the bottom of the http directive:
# include /etc/nginx/snippets/bloxproxy.conf;

# Edit your bloxproxy config
sudo nano /etc/nginx/snippets/bloxproxy.conf
# !! Make sure you change your server name and set your https certificate !!

# Make sure no errors are in the configs
nginx -t
# Expected output: 
nginx: the configuration file /etc/nginx/nginx.conf syntax is ok
nginx: configuration file /etc/nginx/nginx.conf test is successful

# Restart NGINX
sudo systemctl restart nginx
```
Congratulations! You've successfully deployed your own BloxProxy server. You can test it out by using the example url's below.
