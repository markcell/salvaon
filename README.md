#Salvaon
Package for Laravel based on Eloquent to manage XML files.

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

Now, your XML models can simply extend 'Salvaon'.

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
##Help
More help and class reference available soon...