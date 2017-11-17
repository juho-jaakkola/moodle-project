# Composer template for Moodle projects

This in an experimental project template for installing Moodle as a composer
dependency.

This means that both Moodle core and all of the plugins can be managed through
a single `composer.json` file located at the root of the project.

## Getting started with a new Moodle site

Prerequisites are command line access to [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
and [Composer](https://getcomposer.org/doc/00-intro.md).

Change the `your_project` in the following commands to the name of your project.

 1. Clone the template from git `git clone https://github.com/juho-jaakkola/moodle-project.git your_project`
 2. Go to the cloned directory `cd your_project`
 2. Make a new project specific git branch `git checkout -b your_project`
 3. Install Moodle core and the plugins with `composer install`
 4. Install the plugins you need with the `composer require <vendor>/<plugin_name>` command
 5. Commit both `composer.json` and `composer.lock` to git
 6. Push the project to a git repository host
 7. The project can now be duplicated to other environments!

After this it is possible to easily duplicate the site code base to other
environments simply by cloning the branch and running `composer install`.

## Why would I want to use Composer to manage my Moodle project?

 - Managing all the code through a single `composer.json` file makes is possible
   to easily duplicate the code between different environments (developer1,
   developer2, staging, production) so that it is *completely identical*
   between them all.
 - Possibility to update both Moodle core and all third-party plugins to latest
   version (within the version constraints defined in `composer.json`) with a
   single `composer update` command.
 - Possibility for automation
   - For example the `composer install` command could be configured to also
     automatically run upgrades via `admin/cli/upgrade.php`.
 - Composer is de-facto standard package manager for PHP. Learn it once, and
   you will be able to use it with all kinds of popular PHP applications.
