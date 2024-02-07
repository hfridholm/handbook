# Git

- [Configure](#configure)
- [Commands](#commands)

# Configure

To setup Git on Ubuntu, you will first need to install git, which can easily be done with apt, as shown below and in [this tutorial](https://www.youtube.com/watch?v=_kAV059yZ_s&list=PLAyUwmL7et7O8NsNz_7Tn8K8SKgbc0BP6&index=28). 

```bash
sudo apt install git
```

Then you will need to configure both the email and name you want to use.

[git config](https://git-scm.com/docs/git-config)

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

### GitHub SSH

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

# Commands

There are a lot of git commands, so remembering them all is impossible.

- [Repository](#repository)
- [Branching](#branching)
- [Merging](#merging)
- [Stashing](#stashing)
- [Remotes](#remotes)

## Repository

[git init](https://git-scm.com/docs/git-init)

```bash
git init
```

[git clone](https://git-scm.com/docs/git-clone)

```bash
git clone
```

# Branching

[git branch](https://git-scm.com/docs/git-branch)

```bash
git branch <branch>
```

[git checkout](https://git-scm.com/docs/git-checkout)

```bash
git checkout <branch>
```

```bash
git branch --all
```

```bash
git checkout -b <new-branch> <branch>
```

```bash
git branch -d <branch>
```

## Working Tree

[git add](https://git-scm.com/docs/git-add)

```bash
git add
```

[git status](https://git-scm.com/docs/git-status)

```bash
git status
```

[git commit](https://git-scm.com/docs/git-commit)

```bash
git commit
```

[theprimeagen](https://www.youtube.com/shorts/9awOb_q2fhA)

Add changes to the previous commit
```bash
git commit --amend --no-commit
```

[git stash](https://git-scm.com/docs/git-stash)

```bash
git stash
```

[git restore](https://git-scm.com/docs/git-restore)

```bash
git restore
```

[git checkout](https://git-scm.com/docs/git-checkout)

```bash
git checkout
```

[git clean](https://git-scm.com/docs/git-clean)

List files and directories that will be cleaned

```bash
git clean -d -n
```

Remove files and directories

```bash
git clean -d -f
```

## History

[git log](https://git-scm.com/docs/git-log)

```bash
git log --graph --all --oneline
```

[git show](https://git-scm.com/docs/git-show)

```bash
git show <commit>
```

## Merging

### git merge

[git merge](https://git-scm.com/docs/git-merge)

```bash
git merge
```

```bash
git checkout --theirs <file>
```

```bash
git checkout --ours <file>
```

### git rebase

[git rebase](https://git-scm.com/docs/git-rebase)

```bash
git rebase
```

## Stashing

```bash
git stash list
```

```bash
git stash show <stash>
```

```bash
git stash
```

```bash
git stash apply <stash>
```

```bash
git stash pop <stash>
```

```bash
git stash drop <stash>
```

## Remotes

Remotes are a good way of storing repos online. GitHub is a very popular choise.

[git remote](https://git-scm.com/docs/git-remote)

```bash
git remote --verbose
```

```bash
git remote add <remote> <url>
```

```bash
git remote show <remote>
```

```bash
git branch --set-upstream-to=<upstream> <branch>
```

```bash
git remote set-url <remote> <new-url>
```

```bash
git remote remove <remote>
```

### git push

[git push](https://git-scm.com/docs/git-push)

```bash
git push <remote> <branch>
```

```bash
git push 
```

### git fetch

[git fetch](https://git-scm.com/docs/git-fetch)

```bash
git fetch <remote> <branch>
```

### git pull

[git pull](https://git-scm.com/docs/git-pull)

```bash
git pull 
```

## Submodules

```bash
git submodule add <url>
```
