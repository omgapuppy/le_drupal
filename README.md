# le_drupal
Forked from: https://www.drupal.org/project/logentries

The le_drupal module allows Drupal to send watchdog messages to Logentries.

#Installation

* This module requires the library provided by logentries, it has been designed
  to work with version 1.6 of the library, which can be found at:
  https://github.com/logentries/le_php

* Once downloaded extract all files into sites/default/libraries/logentries
  AND
  sites/default/libraries/Logentries/LeLogger.php
  making sure that the LeLogger.php file can be found at
  sites/all/libraries/logentries/LeLogger.php
  AND
  sites/default/libraries/Logentries/LeLogger.php

* Once the library is available enable this module, if you have already enabled
  this module you may need to clear the caches for the library to become
  available.

#Configuration

This module can be configured by going to Configuration->Development->Logging
and errors (admin/config/development/logging) in Drupal, here you can enter
the token provided by Logentries; whether to use SSL to send log messages and
the minimum level of messages to send.
If you want to use different tokens under different circumstances e.g. one for
a development environment and a different one for a live environment, then you
can define the tokens in your settings.php file. An example of this is given
below.

if ($_SERVER['SERVER_ADDR'] == '127.0.0.1') {
  // Local token.
  $conf['logentries_token'] = 'LOGENTRIES_LOCAL_TOKEN';
}
else {
  // Another different token.
  $conf['logentries_token'] = 'LOGENTRIES_ANOTHER_TOKEN';
}
