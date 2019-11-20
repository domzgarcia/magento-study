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
