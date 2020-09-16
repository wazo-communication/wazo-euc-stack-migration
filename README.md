# Wazo EUC Stack migration

This package allows you to transform a community edition of Wazo Platform into a Wazo Enterprise Unified Communication Stack.

This script will add the Wazo EUC repositories and install the packages required to install Wazo EUC Stack.

# Wazo version

Wazo version >= 19.13

# Installation

Connect to your stack and authenticate as user root. Then run the following command:

    apt install wazo-plugind-cli
    wazo-plugind-cli -c "install git https://github.com/wazo-communication/wazo-enterprise-migration"

# Usage

    wazo-enterprise-migration

Read instruction into dialog box.
