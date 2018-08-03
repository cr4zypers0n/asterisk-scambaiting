# Asterisk for Scambaiting
Asterisk config for scambaiting 🧔🏾

## Requirements
You need:
* An account and phone number with [Callcentric](https://callcentric.com).
(Don't worry, it's free.)
* A phone. This could be a softphone on your PC, or a physical IP phone.
* Something to run this on. Preferably 24/7. Maybe a 🥧?

## Usage

### Install Asterisk

#### Debian

Install required packages:
```
apt-get install build-essential openssl libxml2-dev libncurses5-dev uuid-dev sqlite3 libsqlite3-dev pkg-config libjansson-dev
```

Clean any previous Asterisk versions in `/usr/src` directory:
```
cd /usr/src/
rm -rf asterisk*
```

Get Asterisk source:

Asterisk 15
```
wget http://downloads.asterisk.org/pub/telephony/asterisk/asterisk-15-current.tar.gz
```


Compile and install:
```
tar xf asterisk-*-current.tar.gz
cd asterisk-*
./configure
make && make install
```


## Get configuration files

Backup configuration files which come with Asterisk default installation:

```
cd /etc/
mv asterisk asterisk.orig
```

Install `git` (if not already present on your system):
```
apt-get install git-core
```

Install config files
```
git clone https://github.com/cr4zypers0n/asterisk-scambaiting.git asterisk
```

## Update configuration files

Use your favorite text editor to update `sip.conf` file.

Lines that you need to change are clearly indicated.

By default, everyone on your network can call with extension 200 without a password. If you want to add a password, you can use 'secret=lamepassword' in the `extensions.conf` file.

Recordings are stored in `/var/spool/asterisk/monitor` by default.
