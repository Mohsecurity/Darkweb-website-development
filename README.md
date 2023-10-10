# Darkweb-website-development
Step by step procedure on how to create your very own dark web website on any Linux device.
![image](https://github.com/Mohsecurity/Darkweb-website-development/assets/147415543/d554ec20-986e-41d8-afff-5dcf62f793e4)



- Update Linux repository 
- Install Tor 
- Install nginx 


## Update Linux repository
>sudo apt update


## Install Tor
>Sudo apt install tor


### Once Tor is installed we will open its configuration file to make some changes
>sudo nano /etc/tor/torrc


### We will be making two minor changes to our configuration file by commentating this two lines
>#HiddenServiceDir varlib/tor/hidden_service/ - This where your private key and public key
(your .onion address) will be stored<br>

>#HiddenServicePort 80 127.0.0.1:80 – This is what your going to expose to the dark web<br>

### After making those two changes we will have to restart tor services with the following commands
>sudo service tor stop -stop tor services
>sudo service tor start - stop tor services
>sudo service tor status – check the status of tor services
### If you have successfully reached this point your website is already live.
>To check your onion address
>sudo cat /var/lib/tor/hidden_service/hostname
>asjdlajsdkjaklsdjklasjdljsdsj2339jkljdsfds.onion- this is your onion address
### Install nginx
>sudo apt install nginxWe then start Nginx
>sudo service nginx start
>sudo service nginx status
### once we visit our onion address we will be greeted by the default nginx welcome page .
### Before we jump to sharing our onion address we need to make some few security modifications to
### make it safer
>sudo nano /etc/nginx/nginx.conf
### We will be uncommenting these two lines and adding a new line below our server_tokens off line
>server_tokens off;<br>
>port_in_redirect off;<br>
>server_name_in_redirect off;<br>
### Restart Nginx for the changes to take effect
>sudo service nginx restart
### Now we are going to customize our website to our end goal by navigating to
>cd /var/www
>ls
>cd html
>ls
### delete the current file and create a new html filesudo nano index.html
### make your changes and restart nginx
### This is just a basic tutorial on how to create your first Dark web website you can make more
### changes to your liking

![image](https://github.com/Mohsecurity/Darkweb-website-development/assets/147415543/f2348f68-9abb-4ed9-8266-256cc4988faf)
> [!WARNING]
> Hosting a darkweb website on your device is dangerous and users are advised to practice this in a virtual environment so as to minimise the risk of exposing your device to the dangers of the dark net



