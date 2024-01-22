[Official Download](https://docs.nginx.com/nginx/admin-guide/installing-nginx/installing-nginx-open-source/)

[Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04)

```
sudo apt update
sudo apt install nginx
```

```
sudo ufw app list
```

```
Output
Available applications:
  Nginx Full
  Nginx HTTP
  Nginx HTTPS
  OpenSSH
```

```
systemctl status nginx
```

[Certbot Official Download](https://certbot.eff.org/instructions?ws=nginx&os=ubuntufocal)

[Digital Ocean](https://www.digitalocean.com/community/tutorials/how-to-secure-apache-with-let-s-encrypt-on-ubuntu-18-04)

```
sudo apt install certbot python3-certbot-apache
or
sudo apt install certbot python3-certbot-nginx
```
```
sudo certbot --apache
```
