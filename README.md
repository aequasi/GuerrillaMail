# GuerrillaMail

A Simple Library for [GuerrillaMail](http://www.guerrillamail.com).

[![Build Status](https://travis-ci.org/taion809/GuerrillaMail.svg?branch=master)](https://travis-ci.org/taion809/GuerrillaMail)

## Requirements

* PHP 5.3+, however, [PHP 5.5](http://php.net) is recommended.
* PHP's curl extension is required if using the CurlConnection class.

## Installation
This library uses composer, you can install it like so

```json

{
    "require": {
        "johnsn/guerrillamail": "version"
    }
}

```

Replace version with the desired version or branch.  
You can find additional installation details on this project's [packagist page](https://packagist.org/packages/johnsn/guerrillamail)

## Example Usage

```php

<?php
require_once __DIR__.'/vendor/autoload.php';

use GuerrillaMail\GuerrillaConnect\CurlConnection;
use GuerrillaMail\GuerrillaMail;

//The first parameter is the client's IP.
//The second parameter is the client's Browser Agent.
//There is an optional third parameter to set the api endpoint
//There's an optional fourth parameter to set the site domain
//There's an optional fifth parameter to set the API key (only needed if site access is set private)
$connection = new CurlConnection("127.0.0.1", "GuerrillaMail_Library");

//The second parameter is the client's sid (optional)
$gm = new GuerrillaMail($connection);

//Obtain an email address
$response = $gm->get_email_address();

//Fetch user's latest emails.
$emails = $gm->check_email();
```
## TODO:
I haven't given this library the TLC it deserves for awhile due to having a busy schedule so here are the couple of things that I will be taking care of in the next month or two

In no particular order:
  - [ ] Decouple transport from client, currently relies on CurlClient which is not right.
  - [ ] Move to the latest guzzle http client
  - [ ] Use a middleware for authentication
  - [ ] Better documentation and examples

## External links
[GuerrillaMail](http://www.guerrillamail.com) - Guerrilla Mail API doc

https://grr.la/ryo/guerrillamail.com/login/ - Register / login for an API key. (API key is only needed for custom domains.)

## License

This project is licensed under the MIT License.
