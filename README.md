
# Configure Nginx VirtualHost in Ubuntu

configuration of Nginx VirtualHost on Ubuntu. Virtual Hosting is a technique used for hosting multiple domains on a web server


## Reference

[Reference](https://www.youtube.com/watch?v=WEIo9f4QbYM)

  
## Installation


```bash
    //in html directory create new directory
mkdir site

    //change owner
chown -R $USER:$USER /var/www/html/site

    //copy sites-availble/default configuration into above created site
cp /etc/nginx/sites-availble/default /etc/nginx/sites-availble/site.conf

    //edit sites-availble/site.conf
nano /etc/nginx/sites-availble/site.conf

    //change root directory path
root /var/www/html to root /var/www/html/site

    //remove index.nginx-debian.html from list to
index index.html index.htm;

    //set server name
server_name    www.mydomain.com     mydomain

    //sometimes we need to change server port to remove default server;
listen 80;
listen [::]:80;

    //In case of this we have to remove default sites-enabled/default
rm /etc/nginx/sites-enabled/default

    //now enabled newliy created block files using symlink
ln -s /etc/nginx/sites-availble/site.conf /etc/nginx/sites-enabled

    //now check nginx status
nginx -t

    //now restart nginx service
systemctl restart nginx

    //change some settings in host files
nano /etc/hosts

    //now change

example: your_ip_address     www.mydomain.com    mydomain
160.168.1.1         www.mydomain.com    mydomain




```
    
## Feedback

If you have any feedback, please reach out to us at fake@fake.com

  
