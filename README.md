# EasyGoByte-PHP

A simple class for making calls to GoByte's RPC API using PHP.

## Getting Started:
1. Include easygobyte.php into your PHP script:

	`require_once('easygobyte.php');`
2. Initialize GoByte connection/object:

	`$gobyte = new \gobyte\EasyGoByte('username','password');`

	Optionally, you can specify a host, port. Default is HTTP on localhost port 12454.

	`$gobyte = new \gobyte\EasyGoByte('username','password','localhost','12454');`

	If you wish to make an SSL connection you can set an optional CA certificate or leave blank
	`$gobyte->setSSL('/full/path/to/mycertificate.cert');`

3. Make calls to gobyted as methods for your object. Examples:

	`$gobyte->getinfo();`
	`$gobyte->getrawtransaction('0e3e2357e806b6cdb1f70b54c3a3a17b6714ee1f0e68bebb44a74b1efd512098',1);`
	`$gobyte->getblock('000000000019d6689c085ae165831e934ff763ae46a2a6c172b3f1b60a8ce26f');`
	`$gobyte->mnbudget('show');`

## Additional Info:
* When a call fails for any reason, it will return false and put the error message in $gobyte->error

* The HTTP status code can be found in $gobyte->status and will either be a valid HTTP status code or will be 0 if cURL was unable to connect.

* The full response (not usually needed) is stored in $gobyte->response while the raw JSON is stored in $gobyte->raw_response

## Contribution Info

This is forked from
* EasyDash-PHP by By Alexandre (aka elbereth) Devilliers (https://github.com/elbereth/EasyDash-PHP)
* EasyBitcoin-PHP by Andrew LeCody (https://github.com/aceat64/EasyBitcoin-PHP).
Original code is licenced under MIT.
