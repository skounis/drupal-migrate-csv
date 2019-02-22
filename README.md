# Migrate CSV

### Box
- https://www.mamp.info/
- Drush
    - http://docs.drush.org/en/8.x/install/

### Drupal Distribution
- https://www.morethanthemes.com/themes/eventplus

### Install / Enable Modules 
- [Migrate Source CSV](https://www.drupal.org/project/migrate_source_csv)

Download moduel: `drush dl migrate_source_csv`

```
stavross-air-14:csv-migration-example skounis$ drush dl migrate_source_csv
Project migrate_source_csv (8.x-2.2) downloaded to /Applications/MAMP/htdocs/csv-migration-example//modules/migrate_source_csv.       [success]
```

Enable module and depedences `drush en migrate_source_csv`

```
stavross-air-14:csv-migration-example skounis$ drush en migrate_source_csv
The following extensions will be enabled: migrate_source_csv, migrate
Do you really want to continue? (y/n): y
migrate was enabled successfully.                                                                                                                          [ok]
migrate_source_csv was enabled successfully.                                                                                                               [ok]
stavross-air-14:csv-migration-example skounis$ 
```

Clear cache: `drush cr`
