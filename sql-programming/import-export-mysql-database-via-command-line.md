<!-- TITLE: Import/Export Mysql Database Via Command Line -->

To export a MySQL database (as a dump) from the command line run:

```bash
mysqldump -u<username> -p database_name > database_exportname.sql
```

To import a MySQL database dump into a database run:

```bash
mysql -u<username> -p database_name < database_exportname.sql
```

To export all databases into a dump run:

```bash
mysqldump -u<username> -p --all-databases > all_databases_export.sql
```

To import one of the these MySQL databases from the dump into a database run:

```bash
mysql -u<username> -p --one-database database_name < all_databases_export.sql
```