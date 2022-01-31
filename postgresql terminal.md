#### Operating Postgres on terminal using brew

###### check status

```bash
brew services | grep postgresql
```

###### start

```bash
brew services start postgresql
```

###### stop

```bash
brew services stop postgresql
```

###### restart

```bash
brew services restart postgresql
```



#### Operating Postgres on terminal using `pg_ctl`

###### check status

```bash
pg_ctl status
```

###### start

```bash
pg_ctl start
```

```bash
pg_ctl start -D <data-directory>
```



###### stop

```bash
pg_ctl stop
```

###### restart

```bash
pg_ctl restart
```

###### Reload

```bash
pg_ctl reload
```



#### Install a particular version of postgres

```bash
brew install postgresql@<version-number>
```

`brew install postgresql` without specifying the version number will install the latest version. You can downgrade or upgrade to a new version by uninstalling the old version `brew uninstall postgresql@<version>` then install the new version

#### important tips

`BIN DIRECTORY` - `/usr/local/Cellar/postgresql@13/13.4/bin`

`DATA DIRECTORY` -  `/usr/local/var/postgres` 

`Default db` - 	`postgresql`