Ethereum plugin for Dokku
---------------------------

Project: https://github.com/progrium/dokku

**Warning: This plugin is under development and still only tested with the below dependencies**

Requirements
------------

Only tried with the following so far

* Docker version `1.5.0` or higher
* Dokku version `0.3.15` or higher

Installation
------------
```
cd /var/lib/dokku/plugins
git clone https://github.com/alfetopito/dokku-ethereum-plugin/ ethereum
dokku plugins-install
```

Sit tight, the installation usually takes awhile.

Commands
--------
```
$ dokku help
    eth:logs                      Displays the last logs from Ethereum container
    eth:start                     Creates a Ethereum container or starts it if any
    eth:stop                      Stops and removes the Ethereum container if any
```

Simple usage
------------

Start Ethereum cpp client with options `-j -b`

```bash
$ dokku eth:start                  # server side
$ ssh -t dokku@dokku.me eth:start  # client side
```

Stop Ethereum cpp client

```bash
$ dokku eth:stop
```

See the logs

```bash
$ dokku eth:logs
```

TODO
----

* Allow other options to be set
* Start the container automatically

Thanks
------

This plugin was heavily inspired by the dokku varnish plugin https://github.com/Zenedith/dokku-varnish-plugin

