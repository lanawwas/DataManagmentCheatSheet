## Save git bash hisotry in Vscode

- First step: Create the following files

```bash
~/.bash_profile
~/.bashrc
```

- Second Step: Add the following line in both of them

```bash
PROMPT_COMMAND='history -a'
```

To do step 1 and 2 from the console (Git Bash), use the following commands:

```bash
echo "PROMPT_COMMAND='history -a'" >> ~/.bash_profile
echo "PROMPT_COMMAND='history -a'" >> ~/.bashrc
```

### Explaination of the code: 

- What history -a means

    -a append history lines from this session to the history file

- What is PROMPT_COMMAND?

    Bash provides an environment variable called PROMPT_COMMAND. The contents of this variable are executed as a regular Bash command just before Bash displays a prompt.

- Difference between .bash_profile and .bashrc

    .bash_profile is executed for login shells, while .bashrc is executed for interactive non-login shells.

    When somone login (type username and password) via console, either sitting at the machine, or remotely via ssh: .bash_profile is executed to configure your shell before the initial command prompt.

    But, if you’ve already logged into your machine and open a new terminal window (xterm) then .bashrc is executed before the window command prompt. .bashrc is also run when you start a new bash instance by typing /bin/bash in a terminal.

    On OS X, Terminal by default runs a login shell every time, so this is a little different to most other systems, but you can configure that in the preferences.

## SSH keypair setup for GitHub (or GitHub/GitLab/BitBucket, etc, etc)

### Generate a SSH key pair (private/public):

```bash
ssh-keygen -t rsa -C "your_email@example.com"
```

or with more security:
```
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
tag the key with your github email, and use a passphrase as additional security 

### Copy the contents of the public SSH key

```bash
cat ~/.ssh/id_rsa.pub | clip
```

### add the public SSH key to GitHub
Copy the contents of the to your SSH keys to your GitHub account settings (https://github.com/settings/keys).


### Test the SSH key:
```
ssh -T git@github.com
```

Optional: Change url of previous cloned repositories to use ssh instead of http:
```
git remote set-url origin git@github.com:username/your-repository.git
```
If the repo is under an organization the command is slightly different:
```
git remote set-url origin git@github.com:organization/your-repo.git
```

Optional: Add the key to the ssh-agent
```
ssh-add ~/.ssh/id_rsa
```

[reference](https://gist.githubusercontent.com/xirixiz/b6b0c6f4917ce17a90e00f9b60566278/raw/cf3c6333d4894ad76e231be947eb4e3e3c375c37/Set%2520up%2520GitHub%2520push%2520with%2520SSH%2520keys.md)
