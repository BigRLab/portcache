# portcache
A tool to which acts a reverse proxy for remote service with a cache

In microservices world we often end up running services which we don't develop , because they are important for services we develop to run .

portcache will help you to develop your services with out maintaining other services locally . It acts a reverse proxy for remote services
with a cache.

To start portcache: type portcache <config yml file>

The config file requires three params localport , remote , cache_file .
The param localport corresponds to the port you want to run your cache service . You will point your dependent app/service to this port
, the param remote corresponds to the remote url with port that corresponds to the service you would like to cache
and the param cache_file corresponds to the location of the cache you want to save /
A sample file looks like this

localport: 9090
remote: http://myremoteserviceurl.com
cache_file: "/data/tmp/merch

Starting with this config file , whenever a request comes to the localhost:9090 , it will check if this request has been already cached
, if yes then it will serve from cache file , else it will call the http://myremoteserviceurl.com with the request , cache and return the response
