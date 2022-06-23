git 
---

Setting your Git username for every repository on your computer

$ git config --global user.name "XXXXXX"

Setting your Git username for a single repository

Change the current working directory to the local repository where you want to configure the name that is associated with your Git commits.

$ git config user.name "XXXXXXX"

Confirm that you have set the Git username correctly:

$ git config --global user.name

omit --global if you are only want to look at the username configuration in the local repository.

https://git-scm.com/docs/gitignore 

https://github.com/github/gitignore/blob/8ea9c647018521ab2a9c78d630a2fb6579e16d37/Python.gitignore
