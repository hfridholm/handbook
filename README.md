# Ubuntu Guide

1. [Installation](#installation)
2. [Configure System](#configre-system)
3. [Package Management](#package-management)
4. [Useful Commands](#useful-commands)

## Installation

To install an operating system on a computer, you boot up from a medium with the installation program on it, that you then install the system with. In this tutorial, we will use a USB-stick for the simplicity. First you will need to create the live USB-stick, then you might need to configure some settings in the BIOS, and at last you can boot up from the USB-stick and install the operating system on the disk of your choise. 

1. [Create Bootable USB](#create-bootable-usb)
2. [Configure BIOS](#configure-bios)
3. [Install Ubuntu](#install-ubuntu)

[this video](https://www.youtube.com/watch?v=oNEwEQ0uU1Y&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=22)

### Create Bootable USB

To create a live USB-stick with the operating system of your choise, Ubuntu in this case, you will first need to download the Ubuntu ISO from the internet, then you will need to wipe your USB-stick clean, and at last you are going to flash the ISO image to the USB-stick.

1. [Download ISO](#download-iso)
2. [Clean USB](#clean-usb)
3. [Flash ISO to USB](#flash-iso-to-usb)

#### Download ISO

To download the ISO image for the operating system of your choise, you can usually just search for the official website of the operating system and download the ISO from the downloads page.

#### Clean USB

Wipe the USB-stick clean.

#### Flash ISO to USB

To flash the ISO image to the USB-stick, you can use the super simple software [Balena Etcher](https://etcher.balena.io/), which is open source and free to use. It is also cross platform, so it does not matter if the computer you create the live USB-stick has a Windows or a Unix system.

### Configure BIOS



### Install Ubuntu

## Configre Ubuntu system

- [Setup UFW](#setup-ufw)
- [Additional Drivers](#additional-drivers)
- [Create GitHub SSH key](#create-github-ssh-key)

### Setup UFW

[this video](https://www.youtube.com/watch?v=5ATELyEc-_8&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=27)

```bash
$ sudo apt install ufw
```

```bash
$ sudo ufw status
```

```bash
$ sudo ufw disable
```

```bash
$ sudo systemctl status ufw
```

```bash
$ sudo ufw default deny incoming
```

```bash
$ sudo ufw default allow outgoing
```

```bash
$ sudo ufw enable
```

### Additional Drivers

[this video](https://www.youtube.com/watch?v=fHh5yrERvHw&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=10)

### Create GitHub SSH key

[this video](https://www.youtube.com/watch?v=EoLrCX1VVog&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=3&t=109s)

#### Choose the correct graphics driver

## Package Management

- [Installing Packages](#installing-packages)
- [Upgrading System](#upgrading-system)

On Linux operating systems, software and applications are called packages. To download and handle packages, there exist different package managers, that lets the user manage packages in different ways. Some may use a graphical user interface that is easy to use, while other might just rely on the terminal. On Ubuntu, some common package managers are listed below.

- dpkg -
- apt - based on dpkg
- Software Center - based on dpkg

The main differences between the different package managers can be read about [here](https://askubuntu.com/questions/76/whats-the-difference-between-package-managers). Personally I use apt for the most part, for things like upgrading system package dependencies and to install simple programs. There also exists apt-get, and here you can read about [the difference between apt and apt-get](https://askubuntu.com/questions/445384/what-is-the-difference-between-apt-and-apt-get).

### Installing Packages

Often, packages can be installed simply with apt install. Examples of programs that can be installed this way are **vim**, **git** and **uwf**.

```bash
$ sudo apt install <package>
```

Sometimes, packages are downloaded as .deb files and then have to be installed using one of the available package managers. To install .deb files with dpkg you can use the first command, which I have used to download programs like **Minecraft** and **Discord**. And to install .deb files with apt you can use the second command, which I have used to download programs like **Google Chrome**.

```bash
$ sudo dpkg -i file.deb

$ sudo apt install file.deb
```

- [Installing Git](#installing-git)
- [Installing SDL2](#installing-sdl2)

#### Installing Git

To setup Git on Ubuntu, you will first need to install git, which can easily be done with apt, as shown below and in [this tutorial](https://www.youtube.com/watch?v=_kAV059yZ_s&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=28). Then you will need to configure both the email and name you want to use.

```bash
$ sudo apt install git
```

```git
$ git config --global user.email "you@example.com"
$ git config --global user.name "Your Name"
```

#### Installing SDL2

```bash
$ sudo apt-get install libsdl2-dev

$ sudo apt-get install libsdl2-image-dev
```

#### Installing Build Essential

```bash
$ sudo apt install build-essential
```

#### Installing Spotify

[spotify.com](https://www.spotify.com/us/download/linux/)


```bash
$ sudo apt --fix-broken install
```

```bash
$ sudo apt-get -f install
```

### Upgrading System

It is recommended to upgrade the system package dependencies quite often. You can do that easily by using apt. The first command checkes for information about where to download newer versions of packages if so is needed. The second command lists all the packages that can be upgraded. Finally, the third command installs the upgradable packages. For a better explaination, check out [this video](https://www.youtube.com/watch?v=tNT9Hm8fpOA). *Before installing anything else, it is good to update the database of available packages.

```bash
$ sudo apt update

$ apt list --upgradable

$ sudo apt upgrade
```

## Useful Commands
If you want to know what a system program or utility does, you can always check the man page - the system reference manual. The system's manual pager also contains C functions. For more information, the appropriate thing to do, is to check the man page for the man bash command!

```bash
man man
man <program>
```

```bash
$ df --human-readable --print-type --exclude-type=tmpfs
```

```bash
top
```

