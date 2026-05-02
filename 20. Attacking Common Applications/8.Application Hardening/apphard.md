## General Hardening Tips
Secure authentication: Strong passwords, no default creds, 2fa mandatory for at least admins

Access controls: Login pages should not be accessiable from external network and same for file and folders

Disable unsafe features: Like PHP code editing Wordpress

Regular updates:

Backups:

Security Monitoring:

LDAP integration with Active Directory:

## Application-Specific Hardening Tips

WordPress: Use a security plugin such as WordFence which includes security monitoring, blocking of suspicious activity, country blocking, two-factor authentication

Joomla: A plugin such as AdminExile can be used to require a secret key to log in to the Joomla admin page such as http://joomla.inlanefreight.local/administrator?thisismysecretkey

Drupal: Disable, hide, or move the admin login page

Tomcat: Limit access to the Tomcat Manager and Host-Manager applications to only localhost. If these must be exposed externally, enforce IP whitelisting and set a very strong password and non-standard username.

Jenkins: Configure permissions using the Matrix Authorization Strategy plugin

Splunk: Make sure to change the default password and ensure that Splunk is properly licensed to enforce authentication

PRTG Network Monitor: Make sure to stay up-to-date and change the default PRTG password

osTicket: Limit access from the internet if possible

GitLab: Enforce sign-up restrictions such as requiring admin approval for new sign-ups, configuring allowed and denied domains