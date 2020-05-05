# Docker for Jane
- Support Mac OS X and WSL-2
- Current stable version is php7.2

## Requirements
External Source Location
> ~/Storage/Codes/src

## WSL Mount Portable Drive Script
```bash
sudo mount -t drvfs D: /mnt/d
cd /mnt/d
```
## Support SSL for Apache
> https://www.digitalocean.com/community/tutorials/how-to-create-a-ssl-certificate-on-apache-for-ubuntu-14-04
```bash
mkdir /etc/apache2/ssl
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/apache2/ssl/apache.key -out /etc/apache2/ssl/apache.crt
```