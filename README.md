# teller-api
A Full PHP7+ API implementation for Teller.io

# Installation

Install with composer

`composer require philetaylor/teller-api`


# Usage

```php
<?php

// composer require philetaylor/teller

require_once('vendor/autoload.php');

\Teller\Teller::setPersonalAccessToken('YOUR PERSONAL TOKEN');

//echo \Teller\Teller::getPersonalAccessToken();

//var_dump( \Teller\Teller::getAccounts());
\Teller\Teller::setAccount('12312312-9230-4b53-8423-1231b5f0ad0');
//var_dump( \Teller\Teller::getAccount());
//var_dump( \Teller\Teller::getAccount());
//var_dump( \Teller\Teller::getTransactions());
//var_dump( \Teller\Teller::getTransaction('cc918508-1111-4ee9-afa6-a1c615e08262'));
//var_dump( \Teller\Teller::getDirectDebits());
//var_dump( \Teller\Teller::getDirectDebit('023de905-2222-4a12-869c-e9a0414b8426'));
//var_dump( \Teller\Teller::getPayee('096cf26b-a559-3333-a8f0-84245fc9e137'));
//var_dump( \Teller\Teller::getPayees());
//var_dump( \Teller\Teller::getStandingOrders());
```
