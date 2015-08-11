# docksherpa

######Start the files container (contains configuration files)
 - $ docker run --name files sbarnes/files

######Start Couchdb container
 - $ docker run --name couch -p 0.0.0.0:5984:5984 --volumes-from files -v /media/work/docker_db/couchdb:/data -v /media/work/docker_db/log:/usr/local/var/log/couchdb -d mapsherpa/couchdb

######Start Redis container
 - $ docker run --name redis -p 0.0.0.0:6379:6379 -d mapsherpa/redis

---
If using boot2docker run cmd *boot2docker ip* to get the vbox ip address.  This is the ip address that redis and couchdb ports' will be listening on.

