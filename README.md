#Salvaon
Package for Laravel based on Eloquent to manage XML files with SimpleXMLElement and xpath.

##Usage
Install the package through Composer.

```js
{
    "require": {
        "laravel/framework": "4.2.*",
        "markcell/salvaon": "dev-master"
    }
}
```


Edit 'app/config/app.php', and add a new item to the 'aliases' array:

```php
'Salvaon' => 'Markcell\Salvaon\Salvaon'
```


Publish configuration file from package:

```bash
php artisan config:publish markcell/salvaon
```

You may now edit these options at 'app/config/packages/markcell/salvaon/config.php'. Or copy this file to 'app/config' folder with name 'salvaon.php'.


Now, your XML models can simply extend 'Salvaon':

```php
<?php

class Breakfast extends Salvaon {

    /**
     * The file associated with the model
     *
     * @var string
     */
    protected $file = 'breakfast.xml';
   
    /**
     * Root element of the document
     *  
     * @var string
     */
    protected $root = 'breakfast';  
 
    /**
     * Child elements of the root
     * 
     * @var string 
     */
    protected $child = 'food';     
 
    /**
     * The primary key for the model
     *
     * @var string
     */
    protected $primaryKey = 'name';

}
```


See example of 'breakfast.xml' file on this link: 
https://github.com/markcell/salvaon/blob/master/breakfast.xml


##Examples
```php
Breakfast::all();
```
