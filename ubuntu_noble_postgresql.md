Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **PostgreSQL** database server.

If you choose "Instance type" **disk2tb** or **disk4tb**, the directory "/mnt", containing the PostgreSQL data files directory "/mnt/postgresql", is persistent across deletions and recreations of the container. Notice that if you create several containers from this image, each will have it's own data directory - tied to the name of of the container, i.e. the contents of "/mnt" will be different, but persistent, for each container name. If you do not choose instance type, the database data is ephemeral, i.e. gone when the container is gone. With a disk instance type, all databases are also dumped nightly to `postgresql-dump.sql.gz` (pg_dumpall, gzipped) in the folder `Containers` in your ScienceData homedir; when a container starts with an empty disk, this dump is restored.

PostgreSQL runs on the default port 5432 - reverse proxied to a high external port number, which you can inspect in the fold-out panel in the container listing. You can make this number persistent, once the container has started.

You can connect to PostgreSQL from the outside  with your ScienceData certificate and key plus the ScienceData CA certificate - all of which you can download in your [preferences](/index.php/settings/personal#panel-userapps).

You can connect to the database from inside the container with `psql`:
 
```
sudo su - postgres -c psql

psql (16.13 (Ubuntu 16.13-0ubuntu0.24.04.1))
Type "help" for help.

postgres=# SELECT datname FROM pg_database;
  datname  
-----------
 postgres
 template1
 template0
(3 rows)
```

You should run the command `\password postgres` to set a password for the admin user 'postgres'.

You can connect to the database from the outside  with your ScienceData certificate and key plus the ScienceData CA certificate - all of which you can download in your [preferences](/index.php/settings/personal#panel-userapps).

On your container, this has already been done: Thus, on the container, you can test X.509 authentication with:

```
cn=`openssl x509 -in mycert.pem -noout -subject -nameopt compat | sed -E 's|.+/CN=(.+)/.+|\1|'`

psql "host=`hostname` user=$cn dbname=postgres sslmode=verify-full sslcert=mycert.pem sslkey=mykey.pem sslrootcert=/etc/ssl/ca_certs.pem"

psql (16.13 (Ubuntu 16.13-0ubuntu0.24.04.1))
SSL connection (protocol: TLSv1.3, cipher: TLS_AES_256_GCM_SHA384, compression: off)
Type "help" for help.

postgres=# 
```

You can add more users:

```
sudo su - postgres -c "createuser SOME_CN"
```

where 'SOME_CN' is the output of the above `openssl` command with the public certificate of the user to be added as input.

By providing a public SSH key, you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
