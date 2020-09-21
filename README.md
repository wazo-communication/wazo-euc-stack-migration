# Wazo EUC Stack migration

This package allows you to transform a community edition of Wazo Platform into a Wazo Enterprise Unified Communication Stack.

This script will add the Wazo EUC repositories and install the packages required to install Wazo EUC Stack.

## Wazo version

Wazo version >= 19.13

## Installation

Connect to your stack and authenticate as user root. Then run the following command:

```shell
apt install wazo-plugind-cli
wazo-plugind-cli -c "install git https://github.com/wazo-communication/wazo-enterprise-migration"
```

## Usage

```shell
wazo-enterprise-migration
```

### Environment variables

- `CONFD_PORT`: the local port of wazo-confd. Default: `9486`.

## Error codes

### Error 01

Problem: there is no configuration to contact Portal in `/usr/share/wazo-setupd/50-wazo-plugin-nestbox.yml`.

Solution:

- manual intervention
- follow this procedure: https://github.com/TinxHQ/wazo-nestbox-plugin#engine

### Error 02

Problem: the mirror `http://mirror.wazo.community` is still configured.

Diagnostic:

- `apt-cache policy`
- look in `/etc/apt/sources.list.d`

### Error 03

Problem: the mirror `http://mirror.wazo.io` is not correctly configured.

Diagnostic:

- `apt-get update`
- `apt-cache policy`
- look in `/etc/apt/sources.list.d`

### Error 04

Problem: `wazo-confd` is not running

Diagnostic:

- `wazo-service status`
- `systemctl status wazo-confd`
