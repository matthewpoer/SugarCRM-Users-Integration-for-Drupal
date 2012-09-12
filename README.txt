-- SUMMARY --

The SugarCRM Users module allows using an existing SugarCRM users table to control user login and management.
In its current version, the module takes over entirely of the user login form, so users registered via Drupal
will not be allowed to log in (one exception is user #1).

This project is heavily, HEAVILY based on Alon Pe'er's Mediawiki Users modulehttp://drupal.org/node/1780218 (). I used
every bit of his code that I could! Thanks, Alon!

-- REQUIREMENTS --

SugarCRM version 6.0 or above, configured to be accessible via the Drupal web host. Can be CE or Professional version.
PHP's cURL module

-- INSTALLATION --

* Install as usual.

* Enable via admin/modules.

-- CONFIGURATION --

Open settings.php and add the following configuration:

/**
 * The url to the SugarCRM system.
 * INCLUDE a trailing slash
 * DO NOT INCLUDE "index.php"
 * DO NOT INCLUDE the path to web services files
 */
$conf['sugarcrm_users_sugar_url'] = 'http://localhost/sugacrm/';

/**
 * A valid username and password for the SugarCRM system. This user account needs read
 * access to the Users module.
 */
$conf['sugarcrm_users_sugar_username'] = 'admin';
$conf['sugarcrm_users_sugar_password'] = 'password';

/**
 * The user name of user #1.
 * This is required to keep user #1 super admin permissions.
 */
$conf['sugarcrm_users_drupal_admin'] = 'administrator';

-- KNOWN ISSUES --

* The module will break if there are existing users in the Drupal users table with the same user name as a MediaWiki user.

-- CONTACT --

Current maintainer:
Matthew Poer, http://twitter.com/matthewpoer
