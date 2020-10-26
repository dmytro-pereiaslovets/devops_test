# Push all branches from local machine to remote repository

```
 $ git push --all git@github.com:user.name/repo.name.git
```  

# Graph

## Local git branch graphs in terminal 

```
$ git log --all --decorate --oneline --graph
```
## GitHub graph

For GitHub Network graph you need to open:

<https://github.com/dmytro-pereiaslovets/devops_test/network> 

# Current git branch in Bash prompt

## Add to `~/.bashrc`

```
# Show git branch name
function parse_git_branch () {
          git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
  }

RED="\[\033[01;31m\]"
YELLOW="\[\033[01;33m\]"
GREEN="\[\033[01;32m\]"
BLUE="\[\033[01;34m\]"
NO_COLOR="\[\033[00m\]"

# without host
PS1="$GREEN\u$NO_COLOR:$BLUE\w$YELLOW\$(parse_git_branch)$NO_COLOR\$ "

# with host
# PS1="$GREEN\u@\h$NO_COLOR:$BLUE\w$YELLOW\$(parse_git_branch)$NO_COLOR\$ "

```
## Apply changes

```
$ source ~/.bashrc
```
