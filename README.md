# Avahi Aliases (CNAME)

Add `CNAME` aliases to current Avahi host.

Dependencies:
 * Python 2.7
 * python-avahi, python-pip

## Installation

```bash
# apt-get install -y python-avahi python-pip
# pip install --upgrade git+https://github.com/schuellerf/avahi-cname-aliases.git
```

## Systemd configuration
`/etc/systemd/system/avahi-aliases.service` is installed automatically, so you only need to do:
```bash
# systemctl daemon-reload
# systemctl enable avahi-aliases
# systemctl start avahi-aliases
```

## Set aliases
The example `hello.txt` is installed automatically so just create other files like this or modify `/etc/avahi/aliases.d/hello.txt`

```bash
# mkdir /etc/avahi/aliases.d
# echo "hello.local" > /etc/avahi/aliases.d/hello.txt
# systemctl restart avahi-aliases
```

## Common pitfalls

Avahi allows 32 CNAME aliases per group.

In order to increase this value just tune `entries-per-entry-group-max` 
value of `/etc/avahi/avahi-daemon.conf`.


## License

Code is unlicensed. Do whatever you want with it. [Set Your Code Free](http://unlicense.org/).
