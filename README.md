#Salvaon
Package for Laravel based on Eloquent to manage XML files with SimpleXMLElement and xpath.

##Usage
Install the package through Composer.

```js
{
    "require": {
        "laravel/framework": "4.2.*",
        "markcell/salvaon": "dev-master" // or "markcell/salvaon": "1.0.*"
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
// Get all child nodes from XML root.
$foods = Breakfast::all();


// Count elements from selected childs $foods.
$foods->count();


// Get child from XML by $primaryKey or fail if not exists.
Breakfast::findOrFail('French Toast');


// Get child from XML with where condition.
$food = Breakfast::select()->where('name', '=', 'French Toast')->get();

// Update fields from selected child $food. 
$food->price = '3.25€';
$food->calories = 450;

// Save changes.
$food->save();


// Create new XML child.
$new = new Breakfast;

// Add data to child fields.
$new->name = 'French Toast';
$new->price = '4.50€';
$new->description = 'Thick slices made from our homemade sourdough bread';
$new->calories = 600;

// Save new child to XML file with tag attributes.
$new->save(array('id' => 26092014));
```

##License
Code released under the MIT license.
