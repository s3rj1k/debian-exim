# debian-exim

This repository provides exim4 debianized source package for Debian 8.x.

## build dependencies:

```
mkdir -p BUILD && cd BUILD

apt-get update
apt-get -y upgrade
apt-get -y dist-upgrade
apt-get install -y autotools-dev build-essential debhelper devscripts docbook-xml docbook-xsl dpkg-dev libdb5.3-dev libident-dev libmysqlclient-dev libpam0g-dev libpcre3-dev libsasl2-dev libspf2-dev libsqlite3-dev libssl-dev libx11-dev libxaw7-dev libxext-dev libxmu-dev libxt-dev lsb-release lynx po-debconf quilt xsltproc
```

## debian rules:

```
wget --no-check-certificate -qO- https://github.com/s3rj1k/debian-exim/archive/master.tar.gz | tar -xvz --strip=1 -C .
```

## get exim4 sources:

```
wget --no-check-certificate -qO- https://ftp.exim.org/pub/exim/exim4/exim-4.92.tar.gz | tar -xvz --strip=1 --exclude='.gitignore' --exclude='.gitattributes' --exclude='.ctags' -C .
```

## build

```
debuild --no-tgz-check -i -us -uc -b
```
