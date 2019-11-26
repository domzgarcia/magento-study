# key takeaways 

List of common modules and extension servers not yet configured.

[DLL]
----
- C:\laragon\bin\php\php-7.2.11-Win32-VC15-x86\ext

[module] 
----
- mod_rewrite 
- mod_version (x)  

[extensions]
----
- ext-intl  (✓) 
- soap      (✓) 
- opcache   (x) should have add something like this inside php.ini "zend_extension="C:\laragon\bin\php\php-7.2.11-Win32-VC15-x86\ext\php_opcache.dll" "
- enable common opcache config ~ https://www.cloudways.com/blog/integrate-php-opcache/ 

[httpd] to change load modules such mod_version, mod_rewrite
----
- See C:\laragon\bin\apache\httpd-2.4.25-win32-VC14\conf\httpd.conf
- Uncomment "LoadModule version_module modules/mod_version.so" and "LoadModule rewrite_module modules/mod_rewrite.so"
- Restart C:\laragon\etc\apache2\sites-enabled | C:\laragon\etc\nginx\sites-enabled

download
----
https://magento.com/tech-resources/download

- Use credential seen on https://marketplace.magento.com/customer/accessKeys/
- Using Composer | composer create-project --repository=https://repo.magento.com/ magento/project-community-edition <projname>
  
File Permission
----
- vendor rwx
- var rwx
- app/etc rwx
- pub/static rwx

Local Account Sample
----
admin_gkjjuh
magentodb

**Account**
- domsgarcia
- domgarcia.fp@gmail.com
- password123
- magento 111!2

Deployment
----
php bin/magento cache:clean
php bin/magento setup:static-content:deploy -f en_US
php bin/magento deploy:mode:set developer


Issues
----

```md
Re: Can't see Admin Login Page in Magento 2.3 stable release 
It seems that you are using Windows! Magento does not officially support Windows.

This is not an official solution but can fix this issue for using Magento on a Windows machine for development and testing purposes.

1- Open this file:

vendor\magento\framework\View\Element\Template\File\Validator.php

2- Search for this line (around line 138 on version 2.3):

$realPath = $this->fileDriver->getRealPath($path);
3- Replace it with this line: 

$realPath = str_replace("\\", "/", $this->fileDriver->getRealPath($path));
 

This is a very common issue, Many people are not aware of the fact that Magento does not officially support Windows servers! some hacks and un-official modifications such as this one needs to be done in order to make it work on a Windows machine, If you visit the below link "Magento 2.3.x technology stack requirements" you can see that the only supported OS is "Linux x86-64".

https://devdocs.magento.com/guides/v2.3/install-gde/system-requirements-tech.html

I hope this helps and solves your issue.
```


