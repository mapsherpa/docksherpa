#############################################
#    Mapsherpa Couchdb Docker image         #
#############################################

FROM ubuntu:14.04

MAINTAINER Shawn Barnes

# Install and configure CouchDB 1.6.0
RUN ln -sf /usr/share/zoneinfo/EST5EDT /etc/localtime && \
    apt-get update && \
    DEBIAN_FRONTEND=noninteractive && \
    apt-get install -y --force-yes \
    build-essential \
    curl \
    erlang-dev \
    erlang-manpages \
    erlang-base-hipe \
    erlang-eunit \
    erlang-nox \
    erlang-xmerl \
    erlang-inets \
    libmozjs185-dev \
    libicu-dev \
    libcurl4-gnutls-dev \
    libtool && \
    cd /tmp && \
    curl http://mirror.sdunix.com/apache/couchdb/source/1.6.1/apache-couchdb-1.6.1.tar.gz | tar zx && \
    cd apache-couchdb-1.6.1 && \
    ./configure && \
    make && \
    make install && \
    sed -e 's/^bind_address = .*$/bind_address = 0.0.0.0/' -i /usr/local/etc/couchdb/default.ini && \
    sed -e 's/^database_dir = .*$/database_dir = \/data/' -i /usr/local/etc/couchdb/default.ini && \
    sed -e 's/^view_index_dir = .*$/view_index_dir = \/data/' -i /usr/local/etc/couchdb/default.ini && \
		mkdir -p /config/couchdb && \
		touch /config/couchdb/local.ini && \
    ln -sf /config/couchdb/local.ini /usr/local/etc/couchdb/local.ini && \
    apt-get purge -y --auto-remove build-essential && \
    apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#RUN    echo "[admins]" >> /usr/local/etc/couchdb/local.ini 
#RUN    echo "PaddingtonBear = -pbkdf2-4fe0084c36da2857c8e83aa6bc45e2ff82751a65,1b30cff6de6f7921d87ee463d4685b7a,10" >> /usr/local/etc/couchdb/local.ini

# Expose listen port
EXPOSE 5984

# Expose our data, logs and configuration volumes
VOLUME ["/data", "/usr/local/var/log/couchdb", "/usr/local/etc/couchdb", "/etc"]

CMD ["/usr/local/bin/couchdb"]

