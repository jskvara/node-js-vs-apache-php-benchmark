# Installation #

## Debian with Apache ##
Get debian sources from [debian.org/distrib/](http://www.debian.org/distrib/).

There are more posibilities: small image only with core and other is downloaded during installation or large image with all modules included.

For installation follow instructions. Apache is included in standard distribution.

## Node JS ##
Download sources form [nodejs.org](http://nodejs.org)

Install dependent libraries:
```
sudo apt-get install g++ make curl libssl-dev apache2-utils
```

Unzip and install nodeJs:
```
tar xzf node-v0.2.5.tar.gz
cd node-v0.2.5
./configure
make
sudo make install
```