# GUHS CLI

### GRUB UEFI HTTP Selector CLI.
GUHS CLI allows you to install and manage GUHS in your system and expose its configuration into your GUHS Server.

This application it's part of [GRUB UEFI HTTP Selector](https://github.com/jamofer/grub-uefi-http-selector), for
further information please visit the GitHub project.

## Requirements
* Root permissions.
* python3.7.
* Linux OS with UEFI GRUB bootloader.
* GUHS server deployed. (see [GUHS server](https://github.com/jamofer/guhs-server)).

## Installation
```shell
pip3 install guhs-cli
```

## Usage
### GUHS installation
```shell
$ guhs-cli install
GUHS Server hostname/ip? <<user input>>
Available boot targets:
  1. Ubuntu
  2. Ubuntu2
  3. Windows XP
Default target? <<user input>>
Boot selection timeout? <<user_input>>
```

### Show current configuration
```shell
$ guhs-cli show
GUHS status: ENABLED
GUHS HTTP server: 192.168.1.1:8080
Default target: 1. Ubuntu
Boot selection timeout: 10
```

### Show boot targets
```shell
$ guhs-cli ls
1. Ubuntu
2. Ubuntu2
3. Windows XP
```

### Set/Get configuration
```shell
## Set GUHS HTTP server
$ guhs-cli set server=192.168.1.1:80

## Get GUHS HTTP server
$ guhs-cli get server
192.168.1.1:80

## Set boot order
$ guhs-cli set default-target=1
$ guhs-cli set default-target=Ubuntu
$ guhs-cli set default-target=Windows XP

## Set boot selection timeout
$ guhs-cli set boot-selection-timeout=1

## Get boot order
$ guhs-cli get default-target
1
```

### Remove GUHS from GRUB
```shell
$ guhs-cli uninstall
$ guhs-cli show
GUHS was not found in the system. Did you configure it with "guhs-cli configure"?
```
