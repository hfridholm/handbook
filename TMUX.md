# tmux

https://tmuxcheatsheet.com/

List sessions

```bash
tmux ls
```

Kill session

```bash
tmux kill-session -t <id>
```

Rename session

```bash
tmux rename-session -t <id> <name>
```

Create new session

```bash
tmux new-session -s <name>
```

Rename current session

```bash
<prefix> $
```

Detach from current session

```bash
<prefix> d
```

Attach to session

```bash
tmux a -t <id>
```

```bash
tmux attach -t <id>
```

Show every session, window, pane, etc...

```bash
tmux info
```

Split window vertically

```bash
<prefix> %
```

Split window horisontally

```bash
<prefix> "
```

Open new window

```bash
<prefix> c
```

Rename current window

```bash
<prefix> ,
```

Close current window

```bash
<prefix> &
```

List windows

```bash
<prefix> w
```

List sessions

```bash
<prefix> s
```

Switch to n'th window

```bash
<prefix> <n>
```

Close current pane

```bash
<prefix> x
```

Enter command mode

```bash
<prefix> :
```
