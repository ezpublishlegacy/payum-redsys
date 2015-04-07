# Get it started.

In this chapter we are going to talk about the most common task: purchase of a product using [redsys](http://www.redsys.es/).
This gateway is also known as sermepa and is widely used in Spain.

Please note you can't test this gateway if you don't have a merchant account with one of the banks using
this payment gateway. They don't have a public sandbox and we feel sorry about that.

We assume you already read [get it started](https://github.com/Payum/Payum/blob/master/src/Payum/Core/Resources/docs/get-it-started.md) from core.
Here we just show you modifications you have to put to the files shown there.
Remember you need to talk with your bank to get your user data.

## Installation

The preferred way to install the library is using [composer](http://getcomposer.org/).
Run composer require to add dependencies to _composer.json_:

```bash
php composer.phar require crevillo/payum-redsys
```

## config.php

We have to only add the gateway factory. All the rest remain the same:

```php
<?php
//config.php

use Payum\Core\Extension\GenericTokenFactoryExtension;

// ...

$redsysGatewayFactory = new \Crevillo\Payum\Redsys\GatewayFactory;
$gateways['redsys'] = $redsysGatewayFactory->create(array(
   'merchant_code' => 'REPLACE WITH YOURS',
   'terminal' => 'REPLACE WITH YOURS', // normally '001'
   'secret_key' => 'REPLACE WITH YOURS'
   'sandbox' => true
   
    // uncomment if you want notify url to be generated automatically.
    // 'payum.extension.token_factory' => new GenericTokenFactoryExtension($tokenFactory),
));
```

## prepare.php

Here you have to modify a `gatewayName` value. Set it to `redsys`.

## Next 

* [Core's Get it started](https://github.com/Payum/Core/blob/master/Resources/docs/get-it-started.md).
* [The architecture](https://github.com/Payum/Core/blob/master/Resources/docs/the-architecture.md).
* [Supported gateways](https://github.com/Payum/Core/blob/master/Resources/docs/supported-gateways.md).
* [Storages](https://github.com/Payum/Core/blob/master/Resources/docs/storages.md).
* [Capture script](https://github.com/Payum/Core/blob/master/Resources/docs/capture-script.md).
* [Notify script](https://github.com/Payum/Core/blob/master/Resources/docs/notify-script.md).
* [Done script](https://github.com/Payum/Core/blob/master/Resources/docs/done-script.md).

Back to [index](index.md).
