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

Publish configuration file from package:

```bash
php artisan config:publish markcell/salvaon
```

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
Example of 'breakfast.xml' file:

```xml
<?xml version="1.0" encoding="UTF-8"?>
<breakfast>
    <food>
        <name>Belgian Waffles</name>
        <price>$5.95</price>
        <description>Two of our famous Belgian Waffles with plenty of real maple syrup</description>
        <calories>650</calories>
    </food>
    <food>
        <name>Strawberry Belgian Waffles</name>
        <price>$7.95</price>
        <description>Light Belgian waffles covered with strawberries and whipped cream</description>
        <calories>900</calories>
    </food>
    <food>
        <name>Berry-Berry Belgian Waffles</name>
        <price>$8.95</price>
        <description>Light Belgian waffles covered with an assortment of fresh berries and whipped cream</description>
        <calories>900</calories>
    </food>
    <food>
        <name>French Toast</name>
        <price>$4.50</price>
        <description>Thick slices made from our homemade sourdough bread</description>
        <calories>600</calories>
    </food>
    <food>
        <name>Homestyle Breakfast</name>
        <price>$6.95</price>
        <description>Two eggs, bacon or sausage, toast, and our ever-popular hash browns</description>
        <calories>950</calories>
    </food>
</breakfast>

```
##Help
More help and class reference available soon...