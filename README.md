# le_drupal
Forked from: https://www.drupal.org/project/logentries

The le_drupal allows sending Drupal watchdog messages to Logentries.

#Installation

* Requires:
  https://www.drupal.org/project/libraries to be installed & enabled.
  https://github.com/logentries/le_php to be available

* Download and extract Logentries PHP library into "sites/default/libraries/logentries"
  AND
  "sites/default/libraries/logentries"
* Ensure "LeLogger.php" is present in "sites/all/libraries/logentries/LeLogger.php"
  AND
  "sites/default/libraries/logentries/LeLogger.php"
* Upload le_drupal module and enable it

#Configuration

The module settings can be found at Configuration->Development->Logging
and errors (admin/config/development/logging) in Drupal.

You'll find a field for your log token (https://logentries.com/doc/input-token/),
the option to enable / disable SSL and the setting for minimum log level.

If you want to use different tokens under different circumstances e.g. one for
a development environment and a different one for a live environment, then you
can define the tokens in your settings.php file:

if ($_SERVER['SERVER_ADDR'] == '127.0.0.1') {
  // Local token.
  $conf['logentries_token'] = 'LOGENTRIES_LOCAL_TOKEN';
}
else {
  // Another different token.
  $conf['logentries_token'] = 'LOGENTRIES_ANOTHER_TOKEN';
}
