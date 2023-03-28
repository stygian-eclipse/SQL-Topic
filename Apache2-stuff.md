** Sample Apache2 config **

# deny access to _all_ files in the core, including changelog.txt and error.log
# original borrowed from owncloud

# line below if for Apache 2.4
<ifModule mod_authz_core.c>
    Require all denied
</ifModule>

# line below if for Apache 2.2
<ifModule !mod_authz_core.c>
    deny from all
    Satisfy All
</ifModule>

# section for Apache 2.2 and 2.4
IndexIgnore *


** The following lines are not working within apache2.config file....so, I don't know...probably they should be in the .htaccess of the /var/www/html/...whatever folders

# Extra protection added as described by modx documentatiion - NC - 28.03.2023
RewriteCond %{HTTP_POST} ^(www\.)?141.147.49.153\.com$ [NC]

# tryout option 2 - because the site doesn't have yet setup www....etc, yet
RewriteCond %{HTTP_POST} ^(141.147.49.153)$ [NC] 

# Block access to dotfiles and folder people have no need to touch
RewriteRule ^(\.(?!well_known)|_build|gitify|_backup|core|config.core.php) /index.php?q=doesnotexist [L,R=404]

** Useful commands related to Apache2 **
