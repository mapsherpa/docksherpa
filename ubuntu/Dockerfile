#######################################################
#      Ubuntu base image with build tools             #
#######################################################

FROM ubuntu:14.04

## Build tools
RUN apt-get update && apt-get install -y --no-install-recommends \
	autoconf \
	automake \
	bzip2 \
	git \
	file \
	curl \
	g++ \
	gcc \
	imagemagick \
	libbz2-dev \
	libc6-dev \
	libcurl4-openssl-dev \
	libevent-dev \
	libffi-dev \
	libglib2.0-dev \
	libjpeg-dev \
	liblzma-dev \
	libmagickcore-dev \
	libmagickwand-dev \
	libmysqlclient-dev \
	libncurses-dev \
	libpq-dev \
	libreadline-dev \
	libsqlite3-dev \
	libssl-dev \
	libtool \
	libxml2-dev \
	libxslt-dev \
	libyaml-dev \
	make \
	patch \
	xz-utils \
	zlib1g-dev \
	&& apt-get -y clean \
	&& apt-get -y autoclean \
	&& rm -rf /var/lib/apt/lists/*

