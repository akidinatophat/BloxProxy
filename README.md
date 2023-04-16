# BloxProxy
BloxProxy is yet another Roblox API Proxy for HttpService with 3 things in mind:
- Simple
- Reliable
- Configurable

With BloxProxy, say goodbye to dealing with Node.JS and NPM, and long live the hassle of Heroku deployments. All you need is to edit, add, and reload.
If you want to add another Roblox API to BloxProxy, just copy and paste the location directive, edit the url, and reload NGINX. It's that easy.

# Installation
This tutorial is meant for Ubuntu Server. Installing NGINX is different for every distro.

# Step 1: Install packages
Run ```sudo apt update``` to update your repos. Then paste the following:
```sudo apt install nginx certbot```
