# Drupal KIT Docksal Commands
The project uses [Docksal](https://docksal.io/) for local-environment
development and project-building. To get these to install correctly for
your project, make sure that
`".docksal/commands/kit": ["vmlyr-drupal/kit-docksal-commands"],` is set
correctly in the `extra / installer-paths` section of the project's
composer.json file.

 The following is a list of the KIT-specific Docksal commands included:
 - `kit/check-url` – Runs through the collection of URLs listed in the
 `.docksal/configuration.urlcheck.yml` file and checks whether any of
 them return a 200.
 - `kit/check-watchdog` – Counts the current number of errors currently
 listed in a sites watchdog log. This is best used in-tandem with
 check-urls on CI pull-request builds to check whether any of the pages
 are throwing warnings or errors. The builder can then set a threshold
 on allowed number of warnings or errors.
 - `kit/conf` – A wrapper command used in lieu of `drush cex`/`cim`
 which helps handle environment-specific configuration export and import.
 **Please Note: To correctly export _as_ an environment, the environment
 first needs to be imported. The changes can then be made and exported.
 This makes sure that there is no environment cross-polution. Typically,
 importing and exporting as "local" is the most fool-proof way of
 handling configuration unless an environment-specific change needs to
 be made.**
 - `kit/ddrush` – Runs any Drush command inside the project docroot.
 - `kit/eslint` – Run eslint against specified files and/or directories.
 - `kit/init-db` – To initialize or reinitialize one or multiple site's
  databases based on their drush alias files.
 - `kit/init-theme` – Use this command to auto-create new themes based
 on VMLY&R's scaffolding themes.
 - `kit/lint` – Run lint against specified files and/or directories.
 - `kit/phpcbf` – Run Code Beautifier & Fixer (`phpcbf`) against a given
 path.
 - `kit/phpcs` – Run Code Sniffer (`phpcs`) against a given path.
 - `kit/npm` - Run npm in the "source" directory.
 - `kit/gulp` - Run gulp in the "source" directory.
 - `kit/sync` – Sync database (and optionally files) to a local
 environment from an external environment. After the database is
 imported, the site runs various updates and imports configuration as a
 specified (default: local) environment.
