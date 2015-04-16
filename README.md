# CSRF
Simple to use CSRF token class, built by Vundo

## Install

You can install the package via Composer by running ```composer require vundo\csrf``` or by adding ```"vundo/csrf": "dev-master"``` into your require section in your composer.json file. After that, please require the Composer autoloader into your PHP project.

## Generate token

To generate a token, use ```Vundo\CSRF\CSRF::generate();```
### Example
```
<?php
require_once 'vendor/autoload.php';
use Vundo\CSRF\CSRF;

session_start();

$token = CSRF::generate();
?>
```

## Check token

To check a token, use ```Vundo\CSRF\CSRF::check($token);```
### Example
```
<?php
require_once 'vendor/autoload.php';
use Vundo\CSRF\CSRF;

session_start();

if(!CSRF::check($_POST['_token'])) {
	die('Invalid token');
}
?>
```