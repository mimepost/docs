
## Installation

### For [PHP](https://www.php.net/)

## Requirements

PHP 5.5 and later

## Installation & Usage
### Composer

To install the bindings via [Composer](http://getcomposer.org/), run the below command:

```
composer require mimepost/mimepost-php

```

Then run `composer install`

include `autoload.php`:

```php
    require_once('/path/to/mimepost-php/vendor/autoload.php');
```

## Send Email Example

```php

<?php
require_once(__DIR__ . '/vendor/autoload.php');

// Configure API key authorization: api_key
$config = MimePost\Client\Configuration::getDefaultConfiguration()->setApiKey('X-Auth-Token', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = MimePost\Client\Configuration::getDefaultConfiguration()->setApiKeyPrefix('X-Auth-Token', 'Bearer');

$apiInstance = new MimePost\Client\Php\EmailsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

$body = new \MimePost\Client\Model\Email(); // \Swagger\Client\Model\Email | Single Email object
$body->setSubject('This is a subject');
$body->setFromEmail('from@example.com');
$body->setTo(array( array('email' => 'receiver@example.com') )); 
$body->setHtml('<p>This is a test email send using MimePost PHP SDK</p>');

try {
    $result = $apiInstance->sendEmail($body);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling EmailsApi->sendEmail: ', $e->getMessage(), PHP_EOL;
}


```

# Read about 
* [How to create an API token for MimePost](https://mimepost.com/blog/how-to-create-an-api-token-for-mimepost/)

## Documentation for API Endpointsd

* [Read More About API Endpoints](https://github.com/mimepost/mimepost-php/blob/master/README.md)
