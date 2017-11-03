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

Managing all the code through a single `composer.json` file makes is possible
to easily duplicate the code between environments so that it is *completely
identical* between them all.

Some bugs may for example manifest only in some specific plugin versions.
Therefore it is important that all the plugin tested in development
environment get installed to production with identical versions.
