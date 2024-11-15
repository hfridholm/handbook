# Commands

`&&` only runs the next command if the previous one exited with status 0:

```bash
command1 && command2 && command3
```

`;` runs every commands, even if the previous one exits with a non zero status:

```bash
command1; command2; command3
```

If you want to know what a system program or utility does, you can always check the man page - the system reference manual. The system's manual pager also contains C functions. For more information, the appropriate thing to do, is to check the man page for the man bash command!

[man man](https://www.man7.org/linux/man-pages/man1/man.1.html)

```bash
man man
```

```bash
man <program>
```

## Basic

[man ls](https://www.man7.org/linux/man-pages/man1/ls.1.html)

```bash
ls -al
```

[man tree](https://linux.die.net/man/1/tree)

```bash
tree -L <depth>
```

[man cd](https://www.man7.org/linux/man-pages/man1/cd.1p.html)

```bash
cd <directory>
```

```bash
cp <source> <destination>
```

### Move / Rename

[man mv](https://www.man7.org/linux/man-pages/man1/mv.1.html)

```bash
mv <source> <destination>
```

[man rm](https://www.man7.org/linux/man-pages/man1/rm.1.html)

```bash
rm <file>
```

```bash
rm -r <directory>
```

```bash
rm -d <directory>
```

[man rmdir](https://www.man7.org/linux/man-pages/man1/rmdir.1.html)

```bash
rmdir <directory>
```

[man pwd](https://www.man7.org/linux/man-pages/man1/pwd.1.html)

```bash
pwd
```

## Favorite

[man grep](https://www.man7.org/linux/man-pages/man1/grep.1.html)

```bash
grep <pattern>
```

[man df](https://www.man7.org/linux/man-pages/man1/df.1.html)

```bash
df --human-readable --print-type --exclude-type=tmpfs
```

[man top](https://www.man7.org/linux/man-pages/man1/top.1.html)

```bash
top
```

[man w3m](https://linux.die.net/man/1/w3m)

```bash
w3m <url>
```

```bash
feh <image>
```
```bash
sudo apt install feh
```

## Zip
```bash
sudo apt install zip
```

```bash
zip <file>.zip <file>
```

```bash
unzip <file>.zip -d <dir>
```

## netcat

[](https://superuser.com/questions/98089/sending-file-via-netcat)

Send <file>.zip to <address> on <port>
```bash
cat <file>.zip | netcat <address> <port>
```

Receive <file>.zip on <port>
```bash
nc -l -p <port> -q 1 > <file>.zip < /dev/null
```

## Su

Enter root mode
```bash
sudo su
```

Exit root mode, return to normal user mode:
```bash
exit
```

# Jobs

Suspend a process (the current job)
```
[CTRL-Z]
```

Send a process to the background
```
bg
```

List background jobs
```
jobs
```

Start a process in the background
```
<process> &
```

Bring a job from the background to the foreground
```
fg %<jobnum>
```
