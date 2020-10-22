# Laravel Castable Data Transfer Object

[![Latest Version on Packagist](https://img.shields.io/packagist/v/jessarcher/laravel-castable-data-transfer-object.svg?style=flat-square)](https://packagist.org/packages/jessarcher/laravel-castable-data-transfer-object)
[![Build Status](https://img.shields.io/travis/jessarcher/laravel-castable-data-transfer-object/master.svg?style=flat-square)](https://travis-ci.org/jessarcher/laravel-castable-data-transfer-object)
[![Quality Score](https://img.shields.io/scrutinizer/g/jessarcher/laravel-castable-data-transfer-object.svg?style=flat-square)](https://scrutinizer-ci.com/g/jessarcher/laravel-castable-data-transfer-object)
[![Total Downloads](https://img.shields.io/packagist/dt/jessarcher/laravel-castable-data-transfer-object.svg?style=flat-square)](https://packagist.org/packages/jessarcher/laravel-castable-data-transfer-object)

Laravel is awesome. Spatie's data transfer object package for PHP is awesome. They're already good friends, but now they're they're taking their relationship to the next level 💕

Have you ever wanted to cast your JSON columns to a value object? This package gives you a castable version of Spatie's `DataTransferObject` class, called `CastableDataTransferObject`.

Check out the blog post at https://jessarcher.com/blog/casting-json-columns-to-value-objects/

## Installation

You can install the package via composer:

```bash
composer require jessarcher/laravel-castable-data-transfer-object
```

## Usage

### 1. Create your `CastableDataTransferObject`:

``` php
namespace App\Values;

use JessArcher\CastableDataTransferObject\CastableDataTransferObject;

class Address extends CastableDataTransferObject
{
    public string $street;
    public string $suburb;
    public string $state;
}
```

### 2. Configure your Eloquent attribute to cast to it:

Note that this should be `jsonb` or `json` column in your database schema.

```php
namespace App\Models;

use App\Values\Address;
use Illuminate\Database\Eloquent\Model;

class User extends Model
{
    protected $casts = [
        'address' => Address::class
    ];
}
```

And that's it!

### Testing

``` bash
composer test
```

### Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

### Security

If you discover any security related issues, please email jess@jessarcher.com instead of using the issue tracker.

## Credits

- [Jess Archer](https://github.com/jessarcher)
- [All Contributors](../../contributors)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.

## Laravel Package Boilerplate

This package was generated using the [Laravel Package Boilerplate](https://laravelpackageboilerplate.com).