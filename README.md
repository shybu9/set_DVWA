# set_DVWA
setting up DVWA ( damn vuln web app ) in a simple and easy way

![dvwa intro1](https://user-images.githubusercontent.com/112984045/231321297-78c04a8a-1227-4520-8611-949635bcb228.png)

## commands to follow :
```bash
sudo apt update
sudo apt-get update
```

```bash
sudo apt install -y apache2 mariadb-server mariadb-client php php-mysqli php-gd libapache2-mod-php
```
![dvwa apt installs](https://user-images.githubusercontent.com/112984045/231321896-e0a183d0-c4ab-4c38-bfb2-e4b75e9855a9.png)

```bash
cd /var/www/html
```

```bash
sudo git clone git clone https://github.com/digininja/DVWA
```
![dvwa gitclone inhtml](https://user-images.githubusercontent.com/112984045/231324269-92bbf04a-1947-4837-99ae-6aa434dff4cb.png)


## giving the permissions for hosting DVWA
```bash
chmod -R 755 /var/www/html/DVWA
```

```bash
chown -R www-data:www-data /var/www/html/DVWA
```
![dvwa chmod chown](https://user-images.githubusercontent.com/112984045/231324316-cbe9e531-b8bd-4e70-a14a-e65d348655b3.png)


```bash
cd DVWA/config
```

```bash
cp config.inc.php.dist config.inc.php
```

##  you can set/modify the default credentials in config.inc.php using:
```bash
nano config.inc.php
```
![dvwa configsetup](https://user-images.githubusercontent.com/112984045/231323313-09e5b932-0363-4232-8027-ba241899d7b0.png)

##  setting up the database
```bash
service mysql start
```

```bash
mysql -u root -p 
```
`skip the password option (just press enter )`

## enter following commands in mysql shell
```bash
create user '<user name in config.inc.php >'@'127.0.0.1' identified by '<password in config.inc.php >';
```

```bash
grant all privileges on dvwa.* to '<user name in config.inc.php>'@'127.0.0.1' identified by '<password in config.inc.php>';
```
```bash
exit
```
`make sure you exit the mysql shell after executing above commands`

![dvwa mysql enter exit](https://user-images.githubusercontent.com/112984045/231325388-014cf79e-7e66-42ee-98a3-ffa1f4fe0840.png)

## configuring apache2 server
```bash
cd /etc/php/8.2./apache2/
```
`the directory 8.2 my differ according to your version`
```bash
gedit php.ini
```
`in case of no gedit tool try using nano or else go for installing gedit `
![dvwa movingtoapache](https://user-images.githubusercontent.com/112984045/231326536-d74402e9-839e-4330-9f14-046be0e46c29.png)

<br>

`modify to allow_url_fopen = On & allow_url_include = On in line 861 & 865`

![dvwa modifingto on](https://user-images.githubusercontent.com/112984045/231327318-00756a28-a0ac-425a-84cd-2803ff404b4e.png)

`save & exit`

## starting apache server
```bash
service apache2 start
```

## setting up
`search for`
```bash
127.0.0.1/DVWA/setup.php
```
`click on create/reset database`

![dvwa create reset onweb](https://user-images.githubusercontent.com/112984045/231328247-19ec80ec-dd65-4d73-a33a-03270c2c81af.png)

## good to go...
## happy hacking...

<br>
<br>

## do write to shy.bu9@gmail.com

