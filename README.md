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
 4. Install Moodle core and the plugins with `composer install` command
 5. Commit both `composer.json` and `composer.lock` to git

After this it is possible to easily duplicate the site code base to other
environments (development, demo, production etc.) simply by cloning the
branch and running `composer install`.

## Why would I want to use the template?

Managing all the code through a single `composer.json` file makes is possible
to easily duplicate the code between environments so that it is *completely
identical* between them all.

Some bugs may for example manifest only in some specific plugin versions.
Therefore it is important that all the plugin tested in development
environment get installed to production with identical versions.

## Requirements

The project is still experimental stage because it requires some hacks to make
it work.

The `moodle/moodle` package requires two changes:
  1. The package must require the `composer/installers` package so the project
     template becomes able to modify its installation path
  2. The `type` property of the `moodle/moodle` package must be changed from
     `project` to one of the types defined in [list of supported plugin types](https://raw.githubusercontent.com/composer/installers/master/src/Composer/Installers/MoodleInstaller.php).
     so it gets recognised by the `composer/installers` package

Both these changes have currently been made to a custom [composer](https://github.com/juho-jaakkola/moodle/tree/composer)
branch and the project template's `composer.json` has been defined to use that branch.
