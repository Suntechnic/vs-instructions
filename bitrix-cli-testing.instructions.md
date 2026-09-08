---
applyTo: "**/*.php"
---

# Testing Bitrix CLI Scripts

When running, debugging, or testing PHP scripts from the command line, initialize the Bitrix core through the `local/php_interface/tests/Bxx/bitrix.php` bootstrap file.

For direct CLI execution, load the project Composer autoloader before the Bitrix bootstrap:

1. Load `local/php_interface/vendor/autoload.php`.
2. Load `local/php_interface/tests/Bxx/bitrix.php`.
3. Load the target class or execute the test scenario.

Do not include Bitrix core bootstrap files directly, such as `prolog_before.php` or `prolog.php`, when `local/php_interface/tests/Bxx/bitrix.php` is available.

Do not set `$_SERVER['DOCUMENT_ROOT']` manually unless the CLI bootstrap cannot determine the project document root in the current execution environment.