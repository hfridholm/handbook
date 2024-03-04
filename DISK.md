# Disk

[](https://www.youtube.com/watch?v=2Z6ouBYfZr8)

# Useful commands

```bash
df -h
```

Identify the disk by it's size using `lsblk`.
```bash
lsblk
```

Identify the disk by it's metadata using `blkid`
```bash
blkid
```

## Erase and format disk

### Not used links
[](https://askubuntu.com/questions/185815/how-do-i-clear-everything-data-viruses-from-a-thumbdrive)
[](https://askubuntu.com/questions/198065/how-to-format-a-usb-drive)
[](https://askubuntu.com/questions/22381/how-to-format-a-usb-flash-drive)

This guide will show you how to safly erase everything on a USB stick and partition a new filesystem on it for storing new data.

## 1. Identify the disk you want to erase
```bash
lsblk
```

## 2. Erase all the data on the disk (optional)

Replace `/dev/sdX` with the name of your disk
```bash
sudo dd status=progress if=/dev/zero of=/dev/sdX bs=4k && sync
```

## 3. Create partition on empty disk

You can create a partition on the disk by either using `parted` or letting `fdisk` manage it.

### Using `parted`

### 3.1. Create partition table
This creates a DOS partition table with FAT32 primary parition
```bash
sudo parted /dev/sdX mklabel msdos
```

### 3.2. Add an empty primary partition
```bash
sudo parted -a none /dev/sdX mkpart primary fat32 0 2048
```
*NOTE:* The endpoint 2048MB because the disk is only 2GB. Use the max size of your disk

### Using `fdisk` (prefered)

### 3.1. Make a new partition table
This creates a GPT partition table with exFAT primary parition
```bash
sudo fdisk /dev/sdX
```
- Then press letter `g` to create a new empty GPT partition table.

Partition Table Types
GPT - prefered
DOS - supports only 4 primary paritions

### 3.2. Make a new partition
- Press letter `n` to add a new partition. You will be prompted for the size of the partition. Making a primary partition when prompted, if you are not sure.

- Then press letter `w` to write table to disk and exit.

## 4. Format a filesystem on partition

exFAT - prefered
FAT32 - Older and for files smaller than 4GB

### 4.1. Check new partition label
```bash
lsblk
```
The primary parition that you want to create the filesystem on will be the first and only parition `/dev/sdX1`

### 4.2. Format an exFAT filesystem on partition
```bash
sudo mkfs.exfat -n "diskname" /dev/sdX1
```
Or, create a random label for the parition
```bash
sudo mkfs.exfat /dev/sdX1
```
Note: If mkfs.exfat is not installed, you can install it with apt:
Remember to update the repositories
```bash
sudo apt update
```
```bash
sudo apt install exfatprogs exfat-fuse
```
`exfatprogs` is the replacement for the old package called `exfat-utils`.

## 5. Done! Mount the disk, by easily ejecting it and plugging it back in
```bash
sudo eject /dev/sdX
```

# Mounting disks

## Mount directories

media - for temporary disks, like USB flashdrives, and backup storage devices
mnt - for permenant file systems, second hard drive

1. Create directory to mount disk to
For example:
```bash
sudo mkdir /mnt/disk1
```

```bash
sudo mount /dev/sdX /mnt/disk1
```
