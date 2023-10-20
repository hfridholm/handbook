# Ubuntu Guide

1. [Install System](#install-system)
2. [Configure System](#configre-system)
3. [Useful Commands](#useful-commands)

## Install System

To install an operating system, you boot up from a medium with the installation program on it, that you then install the system with. In this tutorial, we will use a USB-stick for the simplicity. First you will need to create the live USB-stick, then you might need to configure some settings in BIOS, and at last you can boot up from the USB-stick and install the operating system on the disk of your choise. For a nice tutorial, watch [this video](https://www.youtube.com/watch?v=oNEwEQ0uU1Y&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=22) by NerdontheStreet on YouTube

1. [Create Bootable USB](#create-bootable-usb)
2. [Configure BIOS](#configure-bios)
3. [Install Ubuntu](#install-ubuntu)

### Create Bootable USB

To create a live USB-stick with the operating system of your choise, Ubuntu in this case, you will first need to download the ISO image from the internet, and then you are going to flash the ISO image to the USB-stick.

1. [Download ISO](#download-iso)
2. [Flash ISO to USB](#flash-iso-to-usb)

#### Download ISO

To download the ISO image, you can usually just search for the official website of the operating system and download the ISO from the downloads page. For Ubuntu, you can visit the official downloads page [here](https://ubuntu.com/download/desktop).

#### Flash ISO to USB

To flash the ISO image to the USB-stick, you can use the super simple software [Balena Etcher](https://etcher.balena.io/), which is open source and free to use. It is also cross platform, so it does not matter if the computer you create the live USB-stick has a Windows or a Unix system.

### Configure BIOS

Configrue BIOS

### Install Ubuntu

Install Ubuntu

## Configre System

- [Package Management](#package-management)
- [Additional Drivers](#additional-drivers)
- [Setup UFW](#setup-ufw)
- [Setup Git](#setup-git)
- [Sync Dotfiles](#sync-dotfiles)
- [Other Packages](#other-packages)

### Package Management

- [Installing Packages](#installing-packages)
- [Upgrading System](#upgrading-system)

On Linux distributions, software and applications are called packages. To download and handle packages, there exist different package managers, that let's the user manage packages in different ways. Some may use a graphical user interface that is easy to use, while other might just rely on the terminal.

The Ubuntu distribution offers these popular package managers:

- `dpkg` -
- `apt` - based on dpkg
- `Software Center` - based on dpkg

The main differences between the different package managers can be read about [here](https://askubuntu.com/questions/76/whats-the-difference-between-package-managers). Personally, I use apt for the most part, for things like upgrading system package dependencies and to install simple programs. There also exists apt-get, and here you can read about [the difference between apt and apt-get](https://askubuntu.com/questions/445384/what-is-the-difference-between-apt-and-apt-get).

#### Installing Packages

Often, packages can simply be installed with apt

Applications that I have downloaded this way: **Vim**, **Git** and **UFW**

```bash
sudo apt install <package>
```

#### Installing .deb files

Sometimes, packages are downloaded as `.deb` files and then have to be installed using one of the available package managers.

##### Installing .deb files using dpkg

Applications that I have downloaded this way: **Minecraft** and **Discord**

```bash
sudo dpkg -i <file>.deb
```

##### Installing .deb files using apt

Applications that I have downloaded this way: **Google Chrome**

```bash
sudo apt install <file>.deb
```

#### Upgrading System

It is recommended to upgrade the system package dependencies quite often. You can do that easily by using `apt`. For a better explaination, check out [this video](https://www.youtube.com/watch?v=tNT9Hm8fpOA). *Before installing anything else, it is good to update the database of available packages.

**Step 1:** Update the information about where to download newer versions of packages if needed.

```bash
sudo apt update
```

List all packages that can be upgraded.

```bash
apt list --upgradable
```

**Step 2:** Install the upgradable packages.

```bash
sudo apt upgrade
```

### Additional Drivers

[this video](https://www.youtube.com/watch?v=fHh5yrERvHw&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=10)

#### Choose the correct graphics driver

### Setup UFW

[this video](https://www.youtube.com/watch?v=5ATELyEc-_8&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=27)

```bash
sudo apt install ufw
```

**Step 1:** bla bla bla

```bash
sudo ufw status
```

**Step 2:** bla bla bla

```bash
sudo ufw disable
```

**Step 3:** bla bla bla

```bash
sudo systemctl status ufw
```

**Step 4:** bla bla bla

```bash
sudo ufw default deny incoming
```

```bash
sudo ufw default allow outgoing
```

**Step 5:** bla bla bla

```bash
sudo ufw enable
```

### Setup Git

To setup Git on Ubuntu, you will first need to install git, which can easily be done with apt, as shown below and in [this tutorial](https://www.youtube.com/watch?v=_kAV059yZ_s&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=28). 

```bash
sudo apt install git
```

Then you will need to configure both the email and name you want to use.

```bash
git config --global user.email "you@example.com"
```

```bash
git config --global user.name "Your Name"
```

Set the default branch name to `master`.

```bash
git config --global init.defaultBranch master
```

[git show](https://stackoverflow.com/questions/424071/how-do-i-list-all-the-files-in-a-commit)

[set upstream](https://stackoverflow.com/questions/520650/make-an-existing-git-branch-track-a-remote-branch)

#### Add GitHub SSH

[this video](https://www.youtube.com/watch?v=EoLrCX1VVog&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=3&t=109s)

**Step 1:** Move to the `.ssh` directory

```bash
cd ~/.ssh
```

**Step 2:** Create the SSH key

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

**Step 3:** Start the SSH agent

```bash
eval $(ssh-agent -s)
```

**Step 4:** Add the newly created SSH key to the agent

```bash
ssh-add ~/.ssh/id_rsa
```

**Step 5:** Output your public key in the terminal, copy the content, and add the key to your GitHub profile.

```bash
cat ~/.ssh/id_rsa.pub
```

### Sync Dotfiles

Dotfiles are...

[H4PE0N's dotfiles](https://github.com/H4PE0N/dotfiles)

### Other Packages

- [Build Essential](#install-build-essential)
- [SDL2](#sdl2)
- [Spotify](#install-spotify)
- [Minecraft](#install-minecraft)
- [Discord](#install-discord)

#### Install Build Essential

```bash
sudo apt install build-essential
```

#### SDL2

```bash
sudo apt-get install libsdl2-dev
```
```bash
sudo apt-get install libsdl2-image-dev
```

#### Install Spotify

[spotify.com](https://www.spotify.com/us/download/linux/)

#### Install Minecraft

[minecraft.net](https://www.minecraft.net/en-us/download)

#### Install Discord

[discord.com](https://discord.com/download)

## Useful Commands
If you want to know what a system program or utility does, you can always check the man page - the system reference manual. The system's manual pager also contains C functions. For more information, the appropriate thing to do, is to check the man page for the man bash command!

```bash
man man
man <program>
```

```bash
df --human-readable --print-type --exclude-type=tmpfs
```

```bash
top
```