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

### Then gg command is to move the cursor to the start of the file

``` 
gg

```


### The yy command is used to yank or copy the current line, but providing the line count can select and copy the number of lines specified 

``` 
yy 

```

 ### Select and Delete All Lines

```
:%d
```
 ### Select and Copy All Lines

```
:%y
```
### Go to the end of the file, use capital G
```
G
```


**sed commands**
----

**ssh commands**
----

ssh -J

**rsync commands**
----

https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories#using-rsync-to-sync-with-a-remote-system

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


** Text Processing*

Copy content of one text file and paste it into another file

cat mockdata_frailty_2021-2.ttl | tee -a mockdata_frailty_2021-LAN.ttl 

https://unix.stackexchange.com/questions/284223/duplicate-the-content-of-a-file

**rst**

https://docutils.sourceforge.io/docs/ref/rst/directives.html#default-role

Reference and Custom anchor
https://sublime-and-sphinx-guide.readthedocs.io/en/latest/references.html#links-to-sections-in-the-same-document

### Bash .sh scripting: 

Got the user input: https://stackoverflow.com/questions/5542016/bash-user-input-if

### Text file to show and follow updates 

```bash
tail -f file.txt: 
```


### Count number of files in a directory

```bash
ls -1 | wc -l
```

### Show directory size

```bash
du -bch
```
Or
```bash
Ls -lh
```

### Show Ubuntu Version

```bash
 lsb_release -a
```
