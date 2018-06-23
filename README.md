# Drupal Meetup Tokyo

## デモ環境

* Landoベース
	* [System Requirements · Lando Documentation](https://docs.devwithlando.io/installation/system-requirements.html)
	* [Installing · Lando Documentation](https://docs.devwithlando.io/installation/installing.html)

## 再現手順

```
git clone git@gitlab.com:snize/drupalTokyo_24.git
cd drupalTokyo_24
lando start
lando composer install
lando drush site:install --sites-subdir=default demo_umami --db-url=mysql://drupal8:drupal8@database/drupal8
lando drush sql:drop
lando drush sql-cli < ./db_24.sql.gz
lando drush config:import
lando drush user:login
```