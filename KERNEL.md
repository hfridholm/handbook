# Linux Kernel

[kernel](https://git.kernel.org/pub/scm/linux/kernel/git/stable/linux.git/tree/drivers/usb/serial?h=v6.6.15)

# WSL2 Kernel

[WSL2 kernel](https://learn.microsoft.com/en-us/community/content/wsl-user-msft-kernel-v6)
[WSL2 kernel](https://unix.stackexchange.com/questions/594470/wsl-2-does-not-have-lib-modules)

Step 1: Clone the Microsoft Linux kernel repository from GitHub
```bash
cd ~/ && git clone https://github.com/microsoft/WSL2-Linux-Kernel.git --depth=1 -b linux-msft-wsl-6.1.y
```

Step 2: Install the required packages to build the kernel
Note: From experience did I add the packages `bc` and `dwarves`
```bash
sudo apt update && sudo apt install build-essential flex bison libssl-dev libelf-dev bc dwarves
```

Step 3: Change directory to the kernel source code
```bash
cd WSL2-Linux-Kernel
```

Step 4: Build the kernel
Note: I did not do this:
```bash
make -j$(nproc) KCONFIG_CONFIG=Microsoft/config-wsl
```
I did this:
```bash
cp Microsoft/config-wsl .config
```
```bash
make -j $(expr $(nproc) - 1)
```

Step 5: Install the kernel modules and headers
```bash
sudo make modules_install headers_install
```

Step 6: Copy the kernel image to the Windows file system
```bash
cp arch/x86/boot/bzImage /mnt/c/Users/<user>/
```
Example:
```bash
cp arch/x86/boot/bzImage /mnt/c/Users/22hamfri/
```

Step 7: Create or edit `.wslconfig` with the following content
```bash
# /mnt/c/<user>/.wslconfig
```
```bash
[wsl2]
kernel=C:\\Users\\<user>\\bzImage
```

Step 8: Open a PowerShell terminal window as Administrator and run following command
```bash
wsl --shutdown
```

Step 9: [Check that WSL is upgraded to WSL2](#upgrade-from-wsl1-to-wsl2)

Step 10: Restart Linux distro for changes to take effect

## Upgrade from WSL1 to WSL2

[WSL2 version](https://dev.to/adityakanekar/upgrading-from-wsl1-to-wsl2-1fl9)

List all distros and the WSL version
```bash
wsl --list --verbose
```

Set the WSL version of a distro
```bash
wsl --set-version <distro-name> 2
```
Example:
```bash
wsl --set-version Ubuntu 2
```

Set the WSL default version for all distros
```bash
wsl --set-default-version 2
```

## Install cp210x driver
[askubuntu.com](https://askubuntu.com/questions/941594/installing-cp210x-driver)
