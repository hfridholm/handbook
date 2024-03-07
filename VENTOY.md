# Ventoy

1. Download .tar.gz file from Ventoy GitHub
[Ventoy GitHub](https://github.com/ventoy/Ventoy)

2. Extract the tar file with gzip compression
```bash
tar -xvzf <file>.tar.gz
```

3. Plugin USB stick, identify and unmount it
```bash
lsblk
```

```bash
sudo umount /dev/sdX 
```

4. Navigate into directory and run Ventoy2Disk.sh
```bash
sudo bash Ventoy2Disk.sh -i /dev/sdX
```

5. Mount the disk, by ejecting it and pluging it back in
```bash
sudo eject /dev/sdX
```

6. Copy your ISO files into the Ventoy directory

7. Done!
