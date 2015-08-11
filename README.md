# docksherpa

Start the files container (contains configuration files)
  $ docker run --name files sbarnes/files

Start Couchdb container
  $ docker run --name couch -p 0.0.0.0:5984:5984 --volumes-from files -v /media/work/docker_db/couchdb:/data -v /media/work/docker_db/log:/usr/local/var/log/couchdb -d mapsherpa/couchdb

Start Redis container
  $ docker run --name redis -p 0.0.0.0:6379:6379 -d mapsherpa/redis

