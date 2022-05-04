# Data-Managment-CheatSheet---Unix-Shell
Draft project: Ongoing work to build a comprehansive cheatsheet for Data managment using Unix Shell .. It is inspired by the Open source community ands

**Midnight Commander**
---

Install
```

sudo apt install mc

```
```
mc
```

**Vim/Vi**

[Reference](https://linuxtect.com/how-to-select-all-in-vim-vi/)

#Then gg command is to move the cursor to the start of the file

``` 
gg

```


 #The yy command is used to yank or copy the current line, but providing the line count can select and copy the number of lines specified 

``` 
yy 

```

 #Select and Delete All Lines

```
:%d
```
 #Select and Copy All Lines

```
:%y
```

**sed commands**
----

**ssh commands**
----

ssh -J

**rsync commands**
----

**mv commands**
----

**cp commands**
----

**scp commands**
----

**history commands**
----

history | grep " "




**wget**
----

curl 
----

shell curl -O https:

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

**Command line operations:**

change directory cd 

create new directory mkdir

delete file 
---
rm -rf 

delete directory 

rm -rdf 

change owner chown

change read/write mode chmod 

mount directory mnt 

list directories ls 

**Java**

Show the default heap memory size

java -XshowSettings:vm

https://dev.to/thegroo/install-and-manage-multiple-java-versions-on-linux-using-alternatives-5e93

Show the project dependencies updates using mvn

https://www.baeldung.com/maven-dependency-latest-version

mvn versions:display-dependency-updates

** Text Processing*

Copy content of one text file and paste it into another file

cat mockdata_frailty_2021-2.ttl | tee -a mockdata_frailty_2021-LAN.ttl 

https://unix.stackexchange.com/questions/284223/duplicate-the-content-of-a-file


