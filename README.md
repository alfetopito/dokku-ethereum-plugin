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
    eth:info                                        Displays Ethereum port, ip and options
    eth:logs                                        Displays the last logs from Ethereum container
    eth:start                                       Creates a Ethereum container or starts it if any
    eth:stop                                        Stops and removes the Ethereum container if any
    eth:version                                     Displays Ethereum version
    eth:link <app>                                  Links <app> to Ethereum container
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

Advanced usage
--------------

Get the current ethereum version

```bash
$ dokku eth:version
```

Get info regarding ethereum host, json port and options used to invoke it

```bash
$ dokku eth:info
```

Link ethereum to an app

```bash
$ dokku eth:link <app>
```

When doing so, the environment variable `ETHEREUM_HOST` will be set for given app.

TODO
----

* Allow other options to be set
* Start the container automatically

Thanks
------

This plugin was heavily inspired by the dokku varnish plugin https://github.com/Zenedith/dokku-varnish-plugin

