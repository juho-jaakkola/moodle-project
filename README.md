# Composer template for Moodle projects

This in an experimental project template for installing Moodle as a composer
dependency.

This means that both Moodle core and all of the plugins can be managed through
a single `composer.json` file located at the root of the project.

## Getting started with a new Moodle site

 1. Clone the template from git
 2. Make a new project specific git branch
 4. Define the plugins needed by the site in the `require` section in
    `composer.json`
 5. Install Moodle core and the plugins with `composer install` command
 6. Commit both `composer.json` and `composer.lock` to git

After this it is possible to easily duplicate the site code base to other
environments (development, demo, production etc.) simply by cloning the
branch and running `composer install`.

## Why would I want to use the template?

 - Managing all the code through a single `composer.json` file makes is possible
   to easily duplicate the code between environments (developer1, developer2,
   staging, production) so that it is *completely
   identical* between them all.
 - Possibility to update both Moodle core and all third-party plugins to latest
   version with one single `composer update` command.
 - Possibility for automation
   - For example the `composer install` command could be configured to also
     automatically run upgrades via `admin/cli/upgrade.php`.
 - Composer is de-facto standard package manager for PHP. Learn it once, and
   you will be able to use it with all kinds of popular PHP applications.
