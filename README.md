# Drupal Meetup Tokyo

## デモ環境

* Landoベース
	* [System Requirements · Lando Documentation](https://docs.devwithlando.io/installation/system-requirements.html)
	* [Installing · Lando Documentation](https://docs.devwithlando.io/installation/installing.html)

## 再現手順

※Landoの利用にはDocker Engineの起動が必要です。

```
git clone git@github.com:snize/drupalTokyo_24.git
cd drupalTokyo_24
lando start
lando composer install
lando drush site:install --sites-subdir=default demo_umami --db-url=mysql://drupal8:drupal8@database/drupal8
lando db-import ./db_24.sql.gz
lando drush config:import
lando drush user:login
```
