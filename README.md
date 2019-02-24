# Drupal Migrate CSV - A working example

### Box
- https://www.mamp.info/
- Drush
    - http://docs.drush.org/en/8.x/install/

### Drupal Distribution
- https://www.morethanthemes.com/themes/eventplus

### Install / Enable Modules 
#### [Migrate Source CSV](https://www.drupal.org/project/migrate_source_csv)

Download module: `drush dl migrate_source_csv`

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

#### [Migrate Plus](migrate_plus)
Download module: `drush dl migrate_plus`

```
stavross-air-14:csv-migration-example skounis$ drush dl migrate_plus
Project migrate_plus (8.x-4.1) downloaded to /Applications/MAMP/htdocs/csv-migration-example//modules/migrate_plus.                                        [success]
Project migrate_plus contains 6 modules: migrate_example_advanced_setup, migrate_example_advanced, migrate_json_example, migrate_example_setup, migrate_example, migrate_plus.
stavross-air-14:csv-migration-example skounis$ 
```

Enable module and depedences `drush en migrate_plus`

```
stavross-air-14:csv-migration-example skounis$ drush en migrate_plus
The following extensions will be enabled: migrate_plus
Do you really want to continue? (y/n): y
migrate_plus was enabled successfully.     
```

#### [Migrate tools](migrate_tools)

Download module: `drush dl migrate_tools`

```
stavross-air-14:csv-migration-example skounis$ drush dl migrate_tools
Project migrate_tools (8.x-4.1) downloaded to /Applications/MAMP/htdocs/csv-migration-example//modules/migrate_tools.                                      [success]
```

Enable module and depedences `drush en migrate_tools`

```
stavross-air-14:csv-migration-example skounis$ drush en migrate_tools
The following extensions will be enabled: migrate_tools
Do you really want to continue? (y/n): y
migrate_tools was enabled successfully.                                                                                                                    [ok]
migrate_tools defines the following permissions: administer migrations   
```

#### [Migrate File](migrate_file)

Download module: `drush dl migrate_file`

```
stavross-air-14:csv-migration-example skounis$ drush dl migrate_file
Project migrate_file (8.x-1.1) downloaded to /Applications/MAMP/htdocs/csv-migration-example//modules/migrate_file.                                        [success]
stavross-air-14:csv-migration-example skounis$ 
```

Enable module and depedences `drush en migrate_file`

```
stavross-air-14:csv-migration-example skounis$ drush en migrate_file
The following extensions will be enabled: migrate_file
Do you really want to continue? (y/n): y
migrate_file was enabled successfully.                                                                                                                     [ok]
stavross-air-14:csv-migration-example skounis$ 
```


- Clear cache: `drush cr`

## Migrate Sponsors

### Prepare CVS
- https://gist.github.com/skounis/8f64fea5ad543a53cb2e2c4eb884c0e6#file-sponsors-06-csv

### Describe the migration
Describe the migration and map the fields 

- [Sponsors `.yml`](https://github.com/skounis/drupal-migrate-csv/blob/master/yml/sponsors.migrate_csv.yml)

#### Import the configuration
- Configuration > Synchronize > Import > Single import
- Configuration type: `Migration`
- Name: `migrate_sponsors`

### Import
Copy the `sponsors.csv` file in a public directory of Drupal. This was defined in the description file in the section:

```
source:
  plugin: csv
  path: public://csv/sponsors.csv
```

#### Run the migration

- migrate: `drush migrate-import migrate_sponsors`

```
stavross-air-14:csv-migration-example skounis$ drush migrate-import migrate_sponsors
Processed 3 items (3 created, 0 updated, 0 failed, 0 ignored) - done with 'migrate_sponsors_3'                    [status]
stavross-air-14:csv-migration-example skounis$ 
```

## References
- https://drushcommands.com/drush-8x/migrate/
- https://www.drupal.org/docs/8/api/migrate-api/executing-migrations
- https://www.drupal.org/docs/8/api/migrate-api/migrate-source-plugins/migrating-data-from-a-csv-source

