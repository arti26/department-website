# department-website

This is website with minimal dummy data of college department created on pantheon platform.


This project contains only the canonical resources used to build a Drupal site for use on Pantheon. There are two different ways that it can be used:
  1.Create a separate canonical repository on GitHub; maintain using a pull request workflow. RECOMMENDED
  2.Build the full Drupal site and then install it on Pantheon; maintain using terminus composer and on-server development.
  The setup instructions vary based on which of these options you select.
-----------------------------------------------------------------------------------------------------------------------------

Use the development tools to help & create Drupal sites faster and with less effort. If you have a favorite Drupal tool that is not listed, make sure we've checked every section of this document. Still can't find the fav? then add it using the format as other listings, similar to: Toolname (Free/Commercial. FOSS/Proprietary. OS Platforms.) - Description.

A Drupal module is a collection of files containing some functionality and is written in PHP. Because the module code executes within the context of the site, it can use all the functions and access all variables and structures of Drupal core. In fact, a module is no different from a regular PHP file that can be independently created and tested and then used to drive multiple functionalities.

------------------------------------------------------------------------------------------------------------------------------


Manual Setup

Enter the commands below to create a a new site on Pantheon and push a copy of this project up to it.

$ SITE="my-site"
$ terminus site:create $SITE "My Site" "Drupal 8" --org="My Team"
$ composer create-project pantheon-systems/example-drops-8-composer $SITE
$ cd $SITE
$ composer prepare-for-pantheon
$ git init
$ git add -A .
$ git commit -m "Initial commit"
$ terminus  connection:set $SITE.dev git
$ PANTHEON_REPO=$(terminus connection:info $SITE.dev --field=git_url)
$ git remote add origin $PANTHEON_REPO
$ git push --force origin master
$ terminus drush $SITE.dev -- site-install --site-name="My Drupal Site"
$ terminus dashboard:view $SITE
------------------------------------------------------------------------------------------------------------------------------
