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

Now, your models can simply extend 'Salvaon'.

```php
<?php

class Dog extends Model {

}
```
##Help
More help and class reference available soon...