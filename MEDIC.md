# Medic

## Enter System
[YouTube Tutorial](https://www.youtube.com/watch?v=t-bdztED6Sg)

**Step 1:** Identify Disk and Partitions
```bash
lsblk
```

```bash
sudo fdisk -l
```

**Step 2:** Mount Filesystem and Boot Partitions
```bash
sudo mount /dev/sda2 /mnt
```

```bash
sudo mount /dev/sda1 /mnt/boot
```

**Step 3:** Change Root into System
```bash
sudo arch-chroot /mnt
```

## Fix System

### Create initramfs Images
```bash
sudo mkinitcpio -P
```

### Reinstall the Kernel
```bash
sudo pacman -S linux
```

### Update Packages
```bash
sudo pacman -Syu
```
