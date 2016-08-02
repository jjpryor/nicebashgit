# nicebashgit
Useful and handy `git` configuration options, and the `.bashrc` changes will
setup a nice bash prompt `PS1` variable that is git branch/status enabled,
will turn on Bash tab-completion for git sub-commands, and will add two aliases
for checking puppet code syntax and styling.

## Known Dependencies
+ Red Hat family OS
+ `rpm` command
+ `git` command

## Credits
+ http://mediadoneright.com/content/ultimate-git-ps1-bash-prompt

## RPM Installation
Run the following in a shell as root.
```bash
yum install bash-completion git
```

## Installation for the git configs
Then as normal user:
```bash
git clone https://github.com/jjpryor/nicebashgit.git
cd nicebashgit
cp -i dot-gitconfig ~/.gitconfig
cp -i dot-gitignore ~/.gitignore
vi ~/.gitconfig`
```
In `~/.gitconfig`, uncomment the two lines and fill in your name & email.


## Test the <TAB> completion and enable BASH PS1 prompt

Then logout.
```shell
exit
```

Then log back in:
```shell
yum i<TAB>
git c<TAB>
cd $HOME
git clone https://github.com/jjpryor/nicebashgit.git
cd nicebashgit
cat append-me-to-dot-bashrc >> ~/.bashrc
cp $(rpm -ql git | grep git-prompt | head -n 1) ~/
exit
```

Then log back in:

