# Configuration #

## Apache modules ##
All unused Apache modules were removed for better performance.

In folder `/etc/apache2/mods-enabled` were only following files:
```
authz_host.load
mime.conf
mime.load
php5.conf
php5.load
```

## Removed headers ##
Lot of headers, that are send by Apache, had to be removed, because NodeJS sends much less headers. These were removed by:

**Remove X-Powered-By:**

In file `/etc/php5/apache2/php.ini` on (line 260) set:
```
expose_php = Off
```

**Remove Server signature:**

In Apache configuration set:
```
ServerSignature Off
ServerTokens Prod
```

**Remove KeepAlive header:**

Set in Apache config:
```
KeepAlive: Off
```

## The resulting response is comparable. ##
**Apache sends these headers:**
```
Date: ...
Server: Apache/2.2.9
Content-Length: 18
Connection: close
Content-Type: text/html
```

**nodeJs sends:**
```
Server: nodeJs
Content-Typte: text/html
Content-Length: 18
Connection: close
```

## Full Apache configuration ##
  * [apache2.conf](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/apache2.conf)
  * [envvars](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/envvars)
  * [ports.conf](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/ports.conf)
  * [security](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/security)
  * [modules-enabled/authz\_host.load](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/modules-enabled/authz_host.load)
  * [modules-enabled/mime.conf](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/modules-enabled/mime.conf)
  * [modules-enabled/mime.load](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/modules-enabled/mime.load)
  * [modules-enabled/php5.conf](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/modules-enabled/php5.conf)
  * [modules-enabled/php5.load](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/modules-enabled/php5.load)
  * [sites-enabled/000-default](http://code.google.com/p/node-js-vs-apache-php-benchmark/source/browse/trunk/sites-enabled/000-default)