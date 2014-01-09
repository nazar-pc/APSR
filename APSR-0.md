Autoloading Standard
====================

The following describes the mandatory requirements that must be adhered to for autoloader interoperability.

Mandatory
---------

* A fully-qualified namespace and class must have the following structure `\<Vendor Name>\(<Namespace>\)*<Class Name>`
* Each namespace must have a top-level namespace ("Vendor Name").
* Each namespace can have as many sub-namespaces as it wishes.
* Each namespace separator is converted to a `/` when loading from the file system.
* The fully-qualified namespace and class is suffixed with `.php` when loading from the file system.
* Alphabetic characters in vendor names, namespaces, and class names should begin with capital letter, underscore is used for word separation

Examples
--------

* `\Symfony\Core\Request` => `/path/to/project/lib/vendor/Symfony/Core/Request.php`
* `\Zend\Acl` => `/path/to/project/lib/vendor/Zend/Acl.php`
* `\Zend\Mail\Message` => `/path/to/project/lib/vendor/Zend/Mail/Message.php`

Underscores in Namespaces and Class Names
-----------------------------------------

* `\namespace\package\Class_Name` => `/path/to/project/lib/vendor/namespace/package/Class_Name.php`
* `\namespace\package_name\Class_Name` => `/path/to/project/lib/vendor/namespace/package_name/Class_Name.php`

Example Implementation
----------------------

Below is an example function to simply demonstrate how the above proposed standards are autoloaded.

```php
<?php

function autoload($className) {
    $className	= ltrim($className, '\\');
    $fileName	= str_replace('_', '/', $className) . '.php';
    require $fileName;
}
```
