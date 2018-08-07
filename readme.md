# Backblaze B2 Cloud Storage for Laravel 5

[![Latest Version on Packagist](https://img.shields.io/packagist/v/imannms/larablaze.svg?style=flat-square)](https://packagist.org/packages/imannms/larablaze)
[![Total Downloads](https://img.shields.io/packagist/dt/imannms/larablaze.svg?style=flat-square)](https://packagist.org/packages/imannms/larablaze)

Backblaze B2 is a great cloud storage system that compares to Amazon S3, but uses lower pricing, so worth the try. ;-)
Since I couldn't find a serviceprovider to implement B2 into the Laravel Filesystem, I wrote one myself. 
Feel free to use it.

This package is forked from [https://github.com/hpolthof/laravel-backblaze](https://github.com/hpolthof/laravel-backblaze)
 
## Installation
Via Composer
```
composer require imannms/larablaze
```

For Laravel 5.5 or higher, the package will automatically register its service provider.

For Laravel 5.4 or bellow, you'll need to register the service provider.
In your app.php config file add to the list of service providers:
```
Imannms\Backblaze\BackblazeServiceProvider::class,
```

Add the following to your filesystems.php config file in the ```disks``` section:
```
'b2' => [
    'driver'         => 'b2',
    'accountId'      => '',
    'applicationKey' => '',
    'bucketName'     => '',
],
```

Now just paste in your credentials and bucketname and you're ready to go!

## Usage
Just use it as you normally would use the Storage facade.
```
\Storage::disk('b2')->put('test.txt', 'test')
```
and
```
\Storage::disk('b2')->get('test.txt')
```

## Credits
* [Paul Olthof](https://github.com/hpolthof)
* [Ramesh Mhetre](https://github.com/mhetreramesh/flysystem-backblaze)
* [Chris White](https://github.com/cwhite92/b2-sdk-php)

## License
MIT