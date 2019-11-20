# key takeaways 

List of common modules and extension servers not yet configured.

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
