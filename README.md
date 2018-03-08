# docker-couchdb-lucene

Run [CouchDB Lucene](https://github.com/rnewson/couchdb-lucene) in a docker container.

```
docker run -d -p 5985:5985 klaemo/couchdb-lucene
```

## Configuration

Both your CouchDB container and the CouchDB Lucene container need to be able to connect to
eachother. This can be done through docker networking. Feel free to take a look at the setup
in the `example` directory.

## CouchDB Lucene

By default the CouchDB Lucene container expects CouchDB to be
reachable at `http://couchdb:5984`. Again this can be achieved with docker networks or container linking.
You can adjust it by doing the following in the couchdb-lucene container (or in a Dockerfile):

```
sed -e 's/couchdb:5984/your-couchdb-hostname:5984/' -i /opt/couchdb-lucene/conf/couchdb-lucene.ini
```

### Proxy handler for CouchDB

Add the following to your CouchDB's `local.ini` or in the configuration UI:
```
[httpd_global_handlers]
_fti = {couch_httpd_proxy, handle_proxy_req, <<"http://couchdb-lucene:5985">>}
```
***Note:*** adjust the URL to couchdb-lucene accordingly.

### Available Tags

* `1.0.2`: CouchDB-Lucene 1.0.2
* `1.1.0`: CouchDB-Lucene 1.1.0
* `2.1.0`, `latest`: CouchDB-Lucene 2.1.0

## Further reading

* [couchdb-lucene](https://github.com/rnewson/couchdb-lucene)
