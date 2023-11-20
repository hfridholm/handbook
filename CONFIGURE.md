# Configure

- [Package Management](#package-management)
- [Additional Drivers](#additional-drivers)
- [Setup UFW](#setup-ufw)
- [Setup Git](#setup-git)
- [Sync Dotfiles](#sync-dotfiles)
- [Other Packages](#other-packages)

## Package Management

- [Installing Packages](#installing-packages)
- [Upgrading System](#upgrading-system)

On Linux distributions, software and applications are called packages. To download and handle packages, there exist different package managers, that let's the user manage packages in different ways. Some may use a graphical user interface that is easy to use, while other might just rely on the terminal.

The Ubuntu distribution offers these popular package managers:

- `dpkg` -
- `apt` - based on dpkg
- `Software Center` - based on dpkg

The main differences between the different package managers can be read about [here](https://askubuntu.com/questions/76/whats-the-difference-between-package-managers). Personally, I use apt for the most part, for things like upgrading system package dependencies and to install simple programs. There also exists apt-get, and here you can read about [the difference between apt and apt-get](https://askubuntu.com/questions/445384/what-is-the-difference-between-apt-and-apt-get).

### Installing Packages

Often, packages can simply be installed with apt

Applications that I have downloaded this way: **Vim**, **Git** and **UFW**

```bash
sudo apt install <package>
```

### Installing .deb files

Sometimes, packages are downloaded as `.deb` files and then have to be installed using one of the available package managers.

#### Installing .deb files using dpkg

Applications that I have downloaded this way: **Minecraft** and **Discord**

```bash
sudo dpkg -i <file>.deb
```

#### Installing .deb files using apt

Applications that I have downloaded this way: **Google Chrome**

```bash
sudo apt install <file>.deb
```

### Upgrading System

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

## Additional Drivers

[this video](https://www.youtube.com/watch?v=fHh5yrERvHw&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=10)

### Choose the correct graphics driver

## Setup UFW

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

## Setup Git

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

### Add GitHub SSH

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

## Install Neovim

[github.com](https://github.com/neovim/neovim/wiki/Building-Neovim)

**Step 1:** Install build prerequisites
```bash
sudo apt-get update
```
```bash
sudo apt-get install ninja-build gettext cmake unzip curl
```

**Step 2:** Move to home directory and clone repo
```bash
cd ~ && git clone https://github.com/neovim/neovim
```

** Step 3:** Move into repo and checkout the stabe version of neovim
```bash
cd neovim && git checkout stable
```

** Step 4:** build neovim
```bash
make CMAKE_BUILD_TYPE=RelWithDebInfo
```

** Step 5:** install neovim from build
```bash
cd build && cpack -G DEB && sudo dpkg -i nvim-linux64.deb
```

### Install Neovim Packages

#### Nvim Tree

#### Lualine

#### Treesitter

#### Telescope

Install ripgrep to search in files

[github.com](https://github.com/BurntSushi/ripgrep)

```bash
sudo apt-get update && sudo apt-get install ripgrep
```

## Install Nerd Fonts

[github.com](https://github.com/ryanoasis/nerd-fonts/)
[youtube.com](https://www.youtube.com/watch?v=cBOaYidGaCQ)

## Sync Dotfiles

Dotfiles are...

[H4PE0N's dotfiles](https://github.com/H4PE0N/dotfiles)

## Other Packages

- [Build Essential](#install-build-essential)
- [SDL2](#sdl2)
- [Spotify](#install-spotify)
- [Minecraft](#install-minecraft)
- [Discord](#install-discord)

### Install Build Essential

```bash
sudo apt install build-essential
```

### SDL2

```bash
sudo apt-get install libsdl2-dev
```
```bash
sudo apt-get install libsdl2-image-dev
```

### Install Spotify

[spotify.com](https://www.spotify.com/us/download/linux/)

### Install Minecraft

[minecraft.net](https://www.minecraft.net/en-us/download)

### Install Discord

[discord.com](https://discord.com/download)

### Install Neofetch

```bash
sudo apt install neofetch
```
