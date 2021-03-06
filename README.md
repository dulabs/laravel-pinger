# Laravel Weblogs Pinger

[![Software License](https://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](LICENSE.md)
[![Laravel Version](https://img.shields.io/badge/laravel-5-orange.svg?style=flat-square)](http://laravel.com)

Weblog system blogs pinger for Laravel 5.

Easy way to notify search engines about your new or updated posts in blog.

## Install

Add

``` JSON
"gaaarfild/laravel-pinger": "~1.0"
```

to your `composer.json` file into `require` section.

Then type in console

``` BASH
$ composer update
```

When update completed, add to your `config/app.conf` file to `providers` section

``` PHP
'providers' => [
    // ...
    Gaaarfild\LaravelPinger\LaravelPingerServiceProvider::class,
]
```

If you want to use `Pinger` facade, add to same file at the `aliases` section

``` PHP
'aliases' => [
    // ...
  'Pinger' => Gaaarfild\LaravelPinger\PingerFacade::class,
]
```

## Usage

### Send ping to services

#### Sending to all services at once

``` php
Pinger::pingAll('Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

#### Send pings to separate services

**Google**

``` php
Pinger::pingGoogle('Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

**Yandex**

``` php
Pinger::pingYandex('Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

**Yahoo**

``` php
Pinger::pingYahoo('Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

**Feedburner**

``` php
Pinger::pingFeedburner('Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

**Weblogs**

``` php
Pinger::pingWeblogs('Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

#### Ping any other service

``` php
Pinger::ping('http://url.of/service', 'Title of post', 'http://url.of/your-post', 'http://url.of/your-rss(optional)');
```

## Contributions

Contributions are highly appreciated.

Send your pull requests to `master` branch.


## License

The MIT License (MIT). Please see [License File](https://github.com/gaaarfild/laravel-pinger/blob/master/LICENSE) for more information.

