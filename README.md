# docker-couchdb-lucene

***work in progress***

```
docker run -d -p 5985:5985 klaemo/couchdb-lucene
```

### Proxy handler for CouchDB

```
[httpd_global_handlers]
_fti = {couch_httpd_proxy, handle_proxy_req, <<"http://127.0.0.1:5985">>}
```

* [couchdb-lucene](https://github.com/rnewson/couchdb-lucene)
