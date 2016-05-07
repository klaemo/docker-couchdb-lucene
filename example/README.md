# docker-couchdb-lucene example

- creates a docker network for the containers so they can talk to each other
- builds and starts a CouchDB container with the appropriate proxy handler config
- starts a `couchdb-lucene` container
- exposes CouchDB on port `5984` on the host network

```
docker-compose up
curl http://localhost:5984
```

Create a database and some docs and then you can start setting up and querying indexes as explained in the [couchdb-lucene readme](https://github.com/rnewson/couchdb-lucene#indexing-strategy).
