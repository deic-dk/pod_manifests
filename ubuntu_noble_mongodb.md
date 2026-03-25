Applying this manifest will start Ubuntu Linux 24.04 LTS (Noble Numbat) - running the OpenSSH server and the **MongoDB** database server.

**Before running this image, you must have generated ScienceData X.509 credentials and have ticked off `Allow internal HTTP access from your own pods` - in your [preferences](/index.php/settings/personal#panel-userapps).**

If you choose "Instance type" **disk2tb** or **disk4tb**, the directory "/mnt", containing the MongoDB data files directory "/mnt/mongodb", is persistent across deletions and recreations of the pod. Notice that if you create several pods from this image, each will have it's own data directory - tied to the name of of the pod, i.e. the contents of "/mnt" will be different, but persistent, for each pod name. If you do not choose instance type, the database data is ephemeral, i.e. gone when the pod is gone.

MongoDB runs on the default port 27017 - reverse proxied to a high external port number, which you can inspect in the fold-out panel in the pod listing. You can make this number persistent, once the pod has started.

You can connect from inside the pod with `mongosh`: 

```
sciencedata@ubuntu-noble-mongodb-fror-dtu-dk:~$ mongosh
Current Mongosh Log ID:	69c402869c79a8ec62d805da
Connecting to:		mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.8.1
Using MongoDB:		undefined
Using Mongosh:		2.8.1

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

test> db.runCommand({connectionStatus: 1})
{
  authInfo: { authenticatedUsers: [], authenticatedUserRoles: [] },
  uuid: UUID('6ce33eb7-ba41-40e4-9d57-e6cf6d5fb6a0'),
  ok: 1
}

```

You should change the admin password. To do this, log in explicitly as 'admin' to the database 'admin':

```
sciencedata@ubuntu-noble-mongodb-fror-dtu-dk:~$ mongosh -u admin -p secret admin
Current Mongosh Log ID:	69c40358dbf0533a93d805da
Connecting to:		mongodb://<credentials>@127.0.0.1:27017/admin?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.8.1
Using MongoDB:		8.2.5
Using Mongosh:		2.8.1

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

admin> db.changeUserPassword('admin', 'mynewverysecretpassword')

```

You can connect to MongoDB from the outside  with your ScienceData certificate and key plus the ScienceData CA certificate - all of which you can download in your [preferences](/index.php/settings/personal#panel-userapps).

On your pod, this has already been done: Thus, on the pod, you can test X.509 authentication with:

```
mongosh --tls --tlsAllowInvalidCertificates --tlsCertificateKeyFile /home/sciencedata/mycertkey.pem --tlsCAFile /etc/ssl/ca_certs.pem --authenticationDatabase '$external' --authenticationMechanism MONGODB-X509
```

and external connectivity with:

```
mongosh --tls --tlsAllowInvalidCertificates --tlsCertificateKeyFile /home/sciencedata/mycertkey.pem --tlsCAFile /etc/ssl/ca_certs.pem --authenticationDatabase '$external' --authenticationMechanism MONGODB-X509 kube.sciencedata.dk:EXTRA_PORT
```

\- where EXTRA_PORT is the external port 27017 has been mapped to.

The data directory "/mnt/mongodb" is backed up nightly to "mongodb.tar.gz" in your ScienceData homedir.

---

By providing a public SSH key, you can access your container via SSH.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).
