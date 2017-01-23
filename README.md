# nicebashgit
Useful and handy `git` configuration options, and the `.bashrc` changes will
setup a nice bash prompt `PS1` variable that is git branch/status enabled,
will turn on Bash tab-completion for git sub-commands, and will add two aliases
for checking puppet code syntax and styling.

![Image of Shell](https://github.com/jjpryor/nicebashgit/raw/master/nicebashgit.png)

In the screenshot above, we can see a coloried and git-aware Bash `PS1` prompt, `<TAB>` completion for git, and color-highlighting in the git output.

## Known Dependencies
+ Red Hat family OS
  - Tested on Fedora 25 and RHEL7.3
+ `rpm` command
+ `git` command

## Credits
+ http://mediadoneright.com/content/ultimate-git-ps1-bash-prompt
+ https://coderwall.com/p/euwpig/a-better-git-log

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
# backup your existing .gitconfig and .gitignore files
cp -p ~/.gitconfig ~/.gitconfig-BAK
cp -p ~/.gitignore ~/.gitignore-BAK
# Now put these in place
cp dot-gitconfig ~/.gitconfig
cp dot-gitignore ~/.gitignore
vi ~/.gitconfig
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
```

## Find the git-prompt.sh and copy it to ~/ and then logout
```shell
cd ~
git clone https://github.com/jjpryor/nicebashgit.git
cd nicebashgit
cat append-me-to-dot-bashrc >> ~/.bashrc
cp $(rpm -ql git git-core | grep git-prompt | head -n 1) ~/.git-prompt.sh
exit
```

Then log back in, and the your bash shell prompt should be much more useful.

## Uninstall
```shell
mv ~/.gitconfig-BAK ~/.gitconfig
mv ~/.gitignore-BAK ~/.gitignore
rm .git-prompt.sh
```
