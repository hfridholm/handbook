# Packages

- [Package Management](#package-management)
- [Favorite Packages](#favorite-packages)

## Package Management

- [Installing Packages](#installing-packages)
- [Upgrading System](#upgrading-system)

On Linux distributions, software and applications are called packages. To download and handle packages, there exist different package managers, that let's the user manage packages in different ways. Some may use a graphical user interface that is easy to use, while other might just rely on the terminal.

The Ubuntu distribution offers these popular package managers:

- `dpkg` -
- `apt` - based on dpkg
- `Software Center` - based on dpkg

The main differences between the different package managers can be read about [here](https://askubuntu.com/questions/76/whats-the-difference-between-package-managers). Personally, I use apt for the most part, for things like upgrading system package dependencies and to install simple programs. There also exists apt-get, and here you can read about [the difference between apt and apt-get](https://askubuntu.com/questions/445384/what-is-the-difference-between-apt-and-apt-get).


See information about a package

```bash
apt-cache policy <package>
```

Search for packages by content keyword, for example the command

```bash
dpkg --search <keyword>
```

Display detailed status information about a package

```bash
dpkg --status <package>
```

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

#### Search Available Packages

```bash
apt-cache search <keyword>
```

### See installed packages

```bash
apt list --installed
```

Check if a package containing the search is installed and what it is called
```bash
apt list --installed | grep <search>
```

### Removing Packages

```bash
sudo apt-get remove <package>
```

```bash
sudo apt purge <package>
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

# Favorite Packages

### Build Essential

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

### ncurses

```bash
sudo apt-get install libncurses5-dev libncursesw5-dev
```

### Spotify

[spotify.com](https://www.spotify.com/us/download/linux/)

### Minecraft

[minecraft.net](https://www.minecraft.net/en-us/download)

### Discord

[discord.com](https://discord.com/download)

### Neofetch

```bash
sudo apt install neofetch
```

### SoX

[man sox](https://linux.die.net/man/1/sox)

```bash
sudo apt install sox
```

### GMP

[GMP](https://gmplib.org/)

```bash
sudo apt install libgmp-dev
```

### Netstat

```bash
sudo apt install net-tools
```

```bash
netstat -lntu
```

### Pdftoppm

```bash
sudo apt install poppler-utils
```

```bash
pdftoppm <pdf> <png> -png
```

### HEIC

[Stack Exchange](https://askubuntu.com/questions/958355/any-app-on-ubuntu-to-open-and-or-convert-heif-pictures-heic-high-efficiency-i)

```bash
sudo apt install heif-gdk-pixbuf heif-thumbnailer
```
