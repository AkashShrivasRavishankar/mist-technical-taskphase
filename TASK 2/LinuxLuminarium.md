# Module Name
Linux Luminarium Module 3
## Challenge Name
cat: not the pet, but the command!

### Solve
**Flag:** `pwn.college{UX4c3hgrJxwOs_c8UWWA-WP59-q.QXxcTN0wCOzYDN0EzW}`

I used ls at first to check what folders/files were available and once i found the flag i just used the cat command and i was able to find the flag

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ ls
a  flag
hacker@commands~cat-not-the-pet-but-the-command:~$ flag
bash: flag: command not found
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{UX4c3hgrJxwOs_c8UWWA-WP59-q.QXxcTN0wCOzYDN0EzW}

```

### New Learnings
Learnt and revised the cat command.

### References 
Info given on Linux Luminarium Modules on pwn.college


## Challenge Name
catting absolute paths

### Solve
**Flag:** `pwn.college{8Zj_nSo9nhyrByDWJTZ1W0qkPb6.QX5ETO0wCOzYDN0EzW}`

This was very straightforward as in the question it was mentioned that the flag lies in the root folder of pwn.college although it typically cannot be accessed, so i just used the absolute path and and used the cat command.

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{8Zj_nSo9nhyrByDWJTZ1W0qkPb6.QX5ETO0wCOzYDN0EzW}
hacker@commands~catting-absolute-paths:~$ 

```

### New Learnings
Learnt and revised the cat command.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
more catting practice

### Solve
**Flag:** `pwn.college{87NBwm9J9CPeij6kI5ZX7dFYxW5.QXwITO0wCOzYDN0EzW}`

This was also very straightforward as in the question it was mentioned that the flag lies in a specified folder so i just did what i did in the last question except i mentioned the entire folder.

```bash
hacker@commands~catting-absolute-paths:~$ 
                                                                                                                                                                                                                                                                                                                                Connected!
You cannot use the 'cd' command in this level, and must retrieve the flag by 
absolute path. Plus, I hid the flag in a different directory! You can find it 
in the file /usr/share/binfmts/flag. Go cat it out **without** cding into that 
directory!
hacker@commands~more-catting-practice:~$ cat /usr/share/binfmts/flag
pwn.college{87NBwm9J9CPeij6kI5ZX7dFYxW5.QXwITO0wCOzYDN0EzW}
hacker@commands~more-catting-practice:~$ 


```

### New Learnings
Learnt and revised the cat command.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
grepping for a needle in a haystackmore catting practice

### Solve
**Flag:** `pwn.college{wOeDafA8B_NpNbVdkT0qeNY0FcI.QX3EDO0wCOzYDN0EzW}`

since we know that the flag always starts with pwn.college, i made use of grep easily, and since the format of the grep command and the location of the flag was given, i just used the given information and found the flag

```bash
                                  Connected!
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep pwn.college /challenge/data.txt
pwn.college{wOeDafA8B_NpNbVdkT0qeNY0FcI.QX3EDO0wCOzYDN0EzW}
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ 
```

### New Learnings
Learnt the grep command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
comparing files
### Solve
**Flag:** `pwn.college{INvre087BCntHwK3VUHy9ArYom-.01MwMDOxwCOzYDN0EzW}`

after understanding how the diff command works, i knew that if there are extra information, it will be printed assuming the remaining content of a file having extra info is exactly the same as the other file, so i implemented this thought and put in the absolute paths of both the files and it worked out.

```bash
Connected!           
hacker@commands~comparing-files:~$ diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
18a19
> pwn.college{INvre087BCntHwK3VUHy9ArYom-.01MwMDOxwCOzYDN0EzW}

```

### New Learnings
Learnt the diff command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
listing files
### Solve
**Flag:** `pwn.college{YpEEq4gjJvAR85DW6DxDVLlo2wh.QX4IDO0wCOzYDN0EzW}`

In this challenge, i first used ls /challenge as instructed and once i got to know the run was actually a file, i simply executed the file and i got the flag. i was using cat at first because i had forgotten you could just open the flag, but after running the file getting the flag was easy

```bash
Connected!           
Connected!           
hacker@commands~listing-files:~$ ls /challenge
15823-renamed-run-2690  DESCRIPTION.md
hacker@commands~listing-files:~$ cat /challenge/DESCRIPTION.md
So far, we've told you which files to interact with.
But directories can have lots of files (and other directories) inside them, and we won't always be here to tell you their names.
You'll need to learn to **l**i**s**t their contents using the `ls` command!

`ls` will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided.
Observe:

```console
hacker@dojo:~$ ls /challenge
run
hacker@dojo:~$ ls
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$ ls /home/hacker
Desktop    Downloads  Pictures  Templates
Documents  Music      Public    Videos
hacker@dojo:~$



In this challenge, we've named `/challenge/run` with some random name!
List the files in `/challenge` to find it.
hacker@commands~listing-files:~$ ls /challenge/15823-renamed-run-2690
/challenge/15823-renamed-run-2690
hacker@commands~listing-files:~$ cd /challenge/15823-renamed-run-2690
bash: cd: /challenge/15823-renamed-run-2690: Not a directory
hacker@commands~listing-files:~$ cat /challenge/15823-renamed-run-2690
#!/opt/pwn.college/bash

echo "Yahaha, you found me! Here is your flag:"
cat /flag
hacker@commands~listing-files:~$ /challenge/15823-renamed-run-2690
Yahaha, you found me! Here is your flag:
pwn.college{YpEEq4gjJvAR85DW6DxDVLlo2wh.QX4IDO0wCOzYDN0EzW}
hacker@commands~listing-files:~$ 

```

### New Learnings
Learnt and revised ls command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
touching files
### Solve
**Flag:** `pwn.college{sCULSbYOSiaY13lOdU6GNm3mEbZ.QXwMDO0wCOzYDN0EzW}`

as the directory of tmp had to be opened while touching the two new files, i first changed my directory and then made the next two files and i was able to get the flag

```bash
Connected!           
Connected!           
hacker@commands~touching-files:~$ ls
a
hacker@commands~touching-files:~$ cd /tmp
hacker@commands~touching-files:/tmp$ touch pwn
hacker@commands~touching-files:/tmp$ touch college
hacker@commands~touching-files:/tmp$ /challenge/run
Success! Here is your flag:
pwn.college{sCULSbYOSiaY13lOdU6GNm3mEbZ.QXwMDO0wCOzYDN0EzW}


```

### New Learnings
Learnt the touch command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
removing files
### Solve
**Flag:** `pwn.college{IsGp-ME2HFh4X01yOioOBeTM2f_.QX2kDM1wCOzYDN0EzW}`

i first used ls to ensure the delete_ me file exists then i used the rm command on the delete_me file, it was straightforward and simple and then i typed /challenge/check to get the flag.

```bash
Connected!           
hacker@commands~removing-files:~$ ls
a  delete_me
hacker@commands~removing-files:~$ rm delete_me
hacker@commands~removing-files:~$ /challenge/check
Excellent removal. Here is your reward:
pwn.college{IsGp-ME2HFh4X01yOioOBeTM2f_.QX2kDM1wCOzYDN0EzW}
hacker@commands~removing-files:~$ 



```

### New Learnings
Learnt the rm command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
moving files
### Solve
**Flag:** `pwn.college{Q-w8OienF82BRp9VJpOdr-x5SmJ.0VOxEzNxwCOzYDN0EzW}`

what i discovered was that in the example given under the challenge, it gave off a more of a renaming of a file kind of a tutorial so i had to research more on it and that's when i realized mv sometimes creates a new folder within a directory if the folder does not exist beforehand. this challenge was fairly straight forward and i only got an error at the beginning because i forgot to type tmp. after that i used mv correctly and got the flag

```bash
hacker@commands~moving-files:~$ mv /flag /hack-the-planet
ERROR: make sure your destination is /tmp/hack-the-planet!
hacker@commands~moving-files:~$ mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
hacker@commands~moving-files:~$ /challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{Q-w8OienF82BRp9VJpOdr-x5SmJ.0VOxEzNxwCOzYDN0EzW}

hacker@commands~moving-files:~$ 


```

### New Learnings
Learnt the mv command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
copying files
### Solve
**Flag:** `pwn.college{8uiO3TE-r-ffqubG1KJN-DFWU9e.0lNxQTMywCOzYDN0EzW}`

the steps were the same as the last challenge, so i used cp with both the files and i got the flag easily, i learnt that the source file does not get deleted in using cp.

```bash
Connected!           
hacker@commands~copying-files:~$ cp /flag /tmp/hack-the-planet
Correct! Performing 'cp /flag /tmp/hack-the-planet'.
hacker@commands~copying-files:~$ /challenge/check
Congrats! You successfully copied the flag to /tmp/hack-the-planet! Here it is:
pwn.college{8uiO3TE-r-ffqubG1KJN-DFWU9e.0lNxQTMywCOzYDN0EzW}



```
### New Learnings
Learnt the cp command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
hidden files
### Solve
**Flag:** `pwn.college{4akf8pSsQJqK7gZ8fJb29-C1IvI.QXwUDO0wCOzYDN0EzW}`

in the challenge it was given that the flag lies in the root folder, so i firstly used ls / -a and only after using ls -a i realised that i saw the flag at the beginning, i tried running it but it wouldn't open so after using cat i got the flag.
```bash
Connected!           
hacker@commands~hidden-files:~$ ls / -a
.                      boot       lib     mnt   run   usr
..                     challenge  lib32   nix   sbin  var
.dockerenv             dev        lib64   opt   srv
.flag-324222053214619  etc        libx32  proc  sys
bin                    home       media   root  tmp
hacker@commands~hidden-files:~$ ls -a
.  ..  .bash_history  .config  a
hacker@commands~hidden-files:~$ /.
bash: /.: Is a directory
hacker@commands~hidden-files:~$ /.flag-324222053214619
bash: /.flag-324222053214619: Permission denied
hacker@commands~hidden-files:~$ cat /..flag-324222053214619
cat: /..flag-324222053214619: No such file or directory
hacker@commands~hidden-files:~$ cat /.flag-324222053214619
pwn.college{4akf8pSsQJqK7gZ8fJb29-C1IvI.QXwUDO0wCOzYDN0EzW}
hacker@commands~hidden-files:~$ 


```

### New Learnings
Learnt the format of hidden files.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
An Epic Filesystem Quest
### Solve
**Flag:** `pwn.college{QSkrVCOCrpHM9jIxuKd-aTyY4HI.QX5IDO0wCOzYDN0EzW}`

this was mostly a rinse and repeat process, and whenever required i had to add a -a while listing the files in order to find hidden files. i repeated the same process, first started from TRACE, read the file and then kept on using the directories from the clue to list the files there, and then used cat. i avoided using cd after the first so that i wouldn't destruct the file. finally by repeating the process, i was able to find the flag.
```bash
hacker@commands~an-epic-filesystem-quest:~$ cd /
hacker@commands~an-epic-filesystem-quest:/$ ls
TRACE  challenge  flag  lib32   media  opt   run   sys  var
bin    dev        home  lib64   mnt    proc  sbin  tmp
boot   etc        lib   libx32  nix    root  srv   usr
hacker@commands~an-epic-filesystem-quest:/$ /flag
bash: /flag: Permission denied
hacker@commands~an-epic-filesystem-quest:/$ cat /flag
cat: /flag: Permission denied
hacker@commands~an-epic-filesystem-quest:/$ cat /TRACE
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/soc/ti

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/$ cd /opt/linux/linux-5.4/drivers/soc/ti
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls
Kconfig     knav_dma.c         pm33xx.c
MESSAGE     knav_qmss.h        ti_sci_inta_msi.c
Makefile    knav_qmss_acc.c    ti_sci_pm_domains.c
built-in.a  knav_qmss_queue.c  wkup_m3_ipc.c
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /TRACE
Great sleuthing!
The next clue is in: /opt/linux/linux-5.4/drivers/soc/ti

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat MESSAGE
Tubular find!
The next clue is in: /usr/share/locale/km

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls usr/share/locale/km
ls: cannot access 'usr/share/locale/km': No such file or directory
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/share/locale/km
LC_MESSAGES  README-TRAPPED
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/locale/km/README-TRAPPED
Tubular find!
The next clue is in: /usr/share/cmake-3.16/Modules/Internal/CPack

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/share/cmake-3.16/Modules/Internal/CPack -a
.                                CPack.VolumeIcon.icns.in
..                               CPack.background.png.in
.MEMO                            CPack.distribution.dist.in
CPack.DS_Store.in                CPackDeb.cmake
CPack.Description.plist.in       CPackExternal.cmake
CPack.Info.plist.in              CPackFreeBSD.cmake
CPack.NuGet.nuspec.in            CPackNuGet.cmake
CPack.OSXScriptLauncher.in       CPackRPM.cmake
CPack.OSXScriptLauncher.rsrc.in  CPackWIX.cmake
CPack.OSXX11.Info.plist.in       CPackZIP.cmake
CPack.OSXX11.main.scpt.in        NSIS.InstallOptions.ini.in
CPack.RuntimeScript.in           NSIS.template.in
CPack.STGZ_Header.sh.in          WIX.template.in
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/cmake-3.16/Modules/Internal/CPack/.MEMO
Lucky listing!
The next clue is in: /usr/share/locale/ti/LC_MESSAGES

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/share/locale/ti/LC_MESSAGES -a
.   .INFO          iso_3166-3.mo  iso_639-2.mo  iso_639.mo
..  iso_3166-1.mo  iso_3166.mo    iso_639-3.mo  iso_639_3.mo
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/locale/ti/LC_MESSAGES/.INFO
Yahaha, you found me!
The next clue is in: /usr/share/gap/lib/hpc
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/share/gap/lib/hpc -a
.  ..  ALERT  tasks.g  thread1.g
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/gap/lib/hpc/ALERT
Congratulations, you found the clue!
The next clue is in: /usr/share/racket/pkgs/typed-racket-lib/typed-racket/static-contracts
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/share/racket/pkgs/typed-racket-lib/typed-racket/static-contracts -a
.            combinators.rkt  kinds.rkt
..           compiled         optimize.rkt
README       constraints.rkt  parametric-check.rkt
TIP          equations.rkt    structures.rkt
combinators  instantiate.rkt  terminal.rkt
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/racket/pkgs/typed-racket-lib/typed-racket/static-contracts/README
Static Contracts:
-----------------

Purpose:
Static contracts are a data structure that correspond to a regular contract.
The two differences are that a static contract corresponds to a contract at a lower phase,
and that they are designed to support introspection and manipulation.

Operations:

various constructors : * -> static-contract?
Construct a static contract corresponding to a regular contract.

optimize : static-contract? [#:trusted-positive boolean? #:trusted-negative boolean?] -> static-contract?
Changes a static contract into another one that is cheaper to check. It also removes contracts
protecting a trusted side.

instantiate : static-contract? (-> A) [kind/c] -> (or/c syntax? A)
Turns a static contract into syntax that when evaluated is the corresponding contract.
The failure continuation is invoked if the translation fails to produce a contract of the right kind.

Internal Implementation Details:

A static contract is one of three things:

recursive-sc:
  This introduces bindings for recursive contracts.
recursive-sc-use:
  This is a reference to a previously introduced recursive contract.
other:
  This is a combinator or terminal contract.

These support a couple of different operations:

sc-map: Calls a function on each sub static contract, and builds up a new static contract
sc-traverse: Calls a function on each sub static contract
sc-terminal-kind: Tells whether a static contract has no subparts and has a known contract kind

These are not applicable to recursive contract; instantaite uses them in its implementation, and
directly deals with the recursive casses.

sc->contract: Turns a static contract into syntax
sc->constraints: Turns a static contract into constraints about the contract kind


hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/racket/pkgs/typed-racket-lib/typed-racket/static-contracts/TIP
Congratulations, you found the clue!
The next clue is in: /usr/share/racket/pkgs/srfi-lib/srfi/%3a6

Watch out! The next clue is **trapped**. You'll need to read it out without 'cd'ing into the directory; otherwise, the clue will self destruct!
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/share/racket/pkgs/srfi-lib/srfi/%3a6 
HINT-TRAPPED  basic-string-ports.rkt  compiled
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/share/racket/pkgs/srfi-lib/srfi/%3a6/HINT-TRAPPED
Tubular find!
The next clue is in: /usr/lib/python3/dist-packages/jedi/inference/__pycache__

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/lib/python3/dist-packages/jedi/inference/__pycache__
__init__.cpython-38.pyc        imports.cpython-38.pyc
analysis.cpython-38.pyc        lazy_value.cpython-38.pyc
arguments.cpython-38.pyc       names.cpython-38.pyc
base_value.cpython-38.pyc      param.cpython-38.pyc
cache.cpython-38.pyc           parser_cache.cpython-38.pyc
context.cpython-38.pyc         recursion.cpython-38.pyc
docstrings.cpython-38.pyc      signature.cpython-38.pyc
dynamic_params.cpython-38.pyc  star_args.cpython-38.pyc
filters.cpython-38.pyc         syntax_tree.cpython-38.pyc
finder.cpython-38.pyc          sys_path.cpython-38.pyc
flow_analysis.cpython-38.pyc   usages.cpython-38.pyc
helpers.cpython-38.pyc         utils.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ ls /usr/lib/python3/dist-packages/jedi/inference/__pycache__ -a
.                              helpers.cpython-38.pyc
..                             imports.cpython-38.pyc
.CLUE                          lazy_value.cpython-38.pyc
__init__.cpython-38.pyc        names.cpython-38.pyc
analysis.cpython-38.pyc        param.cpython-38.pyc
arguments.cpython-38.pyc       parser_cache.cpython-38.pyc
base_value.cpython-38.pyc      recursion.cpython-38.pyc
cache.cpython-38.pyc           signature.cpython-38.pyc
context.cpython-38.pyc         star_args.cpython-38.pyc
docstrings.cpython-38.pyc      syntax_tree.cpython-38.pyc
dynamic_params.cpython-38.pyc  sys_path.cpython-38.pyc
filters.cpython-38.pyc         usages.cpython-38.pyc
finder.cpython-38.pyc          utils.cpython-38.pyc
flow_analysis.cpython-38.pyc
hacker@commands~an-epic-filesystem-quest:/opt/linux/linux-5.4/drivers/soc/ti$ cat /usr/lib/python3/dist-packages/jedi/inference/__pycache__/.CLUE
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{QSkrVCOCrpHM9jIxuKd-aTyY4HI.QX5IDO0wCOzYDN0EzW}

```

### New Learnings
Revised my knowledge on cd,ls and cat commands as well as the format of hidden files.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
making directories
### Solve
**Flag:** `pwn.college{8FqiwMJgRq1PEBvgA1C83guaH3i.QXxMDO0wCOzYDN0EzW}`

i first changed the directory to tmp so i could make a directory there, after making the directory i changed my directory to the created directory so i could create a file there as asked in the challenge and then i was able to find the flag.
```bash
Connected!           
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{8FqiwMJgRq1PEBvgA1C83guaH3i.QXxMDO0wCOzYDN0EzW}

```

### New Learnings
Learnt the format of hidden files.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
finding files
### Solve
**Flag:** `pwn.college{QC6NdbLYs8DLT-N4BKoanuwdmMj.QXyMDO0wCOzYDN0EzW}`

as mentioned, the find command took a lot more time than i thought it would, after which i executed the entire directories of the accessable flag locations, where i saw there was only one file which had permission denied on it, so i assumed it's not an executable file and it was a text file which could be read by the cat command so i used it and i found the flag!
```bash
Connected!           
hacker@commands~making-directories:~$ cd /tmp
hacker@commands~making-directories:/tmp$ mkdir pwn
hacker@commands~making-directories:/tmp$ cd pwn
hacker@commands~making-directories:/tmp/pwn$ touch college
hacker@commands~making-directories:/tmp/pwn$ /challenge/run
Success! Here is your flag:
pwn.college{8FqiwMJgRq1PEBvgA1C83guaH3i.QXxMDO0wCOzYDN0EzW}
hacker@commands~making-directories:/tmp/pwn$ ^C
hacker@commands~making-directories:/tmp/pwn$ 
                                                                                                                                                                                                                                                                                                                                                                              Connected!           
hacker@commands~finding-files:~$ find / -name flag
find: ‘/root’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/tmp/tmp.2dyEZcT2Od’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/etc/ssl/private’: Permission denied

/usr/local/lib/python3.8/dist-packages/pwnlib/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_internal/utils/__pycache__/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
hacker@commands~finding-files:~$ 
hacker@commands~finding-files:~$ /usr/local/lib/python3.8/dist-packages/pwnlib/flag
bash: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
bash: /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ /nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
bash: /nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ /nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
bash: /nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
hacker@commands~finding-files:~$ /opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_internal/utils/__pycache__/flag
bash: /opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_internal/utils/__pycache__/flag: Permission denied
hacker@commands~finding-files:~$ /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
bash: /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ /usr/local/lib/python3.8/dist-packages/pwnlib/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_internal/utils/__pycache__/flag
/nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag
/nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag
/nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag
/nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag
/nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag
/nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag
bash: /usr/local/lib/python3.8/dist-packages/pwnlib/flag: Is a directory
bash: /opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag: Is a directory
bash: /opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_internal/utils/__pycache__/flag: Permission denied
bash: /nix/store/7ns27apnvn4qj4q5c82x0z1lzixrz47p-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
bash: /nix/store/5z3sjp9r463i3siif58hq5wj5jmy5m98-python3.12-pwntools-4.13.1/lib/python3.12/site-packages/pwnlib/flag: Is a directory
bash: /nix/store/5n5lp1m8gilgrsriv1f2z0jdjk50ypcn-rizin-0.7.3/share/rizin/flag: Is a directory
bash: /nix/store/bnlabj2vsbljhp597ir29l51nrqhm89w-rizin-0.7.4/share/rizin/flag: Is a directory
bash: /nix/store/s8b49lb0pqwvw0c6kgjbxdwxcv2bp0x4-radare2-5.9.8/share/radare2/5.9.8/flag: Is a directory
bash: /nix/store/1hyxipvwpdpcxw90l5pq1nvd6s6jdi5m-python3.12-pwntools-4.14.1/lib/python3.12/site-packages/pwnlib/flag: Is a directory
bash: /nix/store/h88mxp2mbgyj06vypwmqpy05idhwimnp-python3.13-pwntools-4.14.1/lib/python3.13/site-packages/pwnlib/flag: Is a directory
bash: /nix/store/5qz6hgb1qzpvjrsw20wyiylx5zw8b9bk-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag: Is a directory
hacker@commands~finding-files:~$ ^C
hacker@commands~finding-files:~$ cat /opt/pwndbg/.venv/lib/python3.8/site-packages/pip/_internal/utils/__pycache__/flag
pwn.college{QC6NdbLYs8DLT-N4BKoanuwdmMj.QXyMDO0wCOzYDN0EzW}hacker@commands~finding-files:~$ 

```

### New Learnings
Learnt the find command and used my knowledge of cat command.
### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
symbolic files
### Solve
**Flag:** `pwn.college{MZn7XzgSxSqZy50223Q9zwC6Z46.QX5ETN1wCOzYDN0EzW}`

firstly, i used the file command on all the 3 files to figure out what kind of files they are, i figured out that the 'not-the'flag' file does not exist, meaning i could use the symlinking with not the flag to the actual flag. after i linked it, i was using cat on /challenge/catflag instead of simply running /challenge/catflag, which was my mistake which made me confused on if i did the right step and i was using different commands till i realised that /challenge/catflag is a script and not a symlink so using cat on it was the wrong move, so i ran /challenge/catflag and found the flag.
```bash
Connected!           
Connected!           
hacker@commands~linking-files:~$ file /flag
/flag: regular file, no read permission
hacker@commands~linking-files:~$ file /challenge/catflag
/challenge/catflag: setuid a /opt/pwn.college/bash script, ASCII text executable
hacker@commands~linking-files:~$ file ~/not-the-flag
/home/hacker/not-the-flag: cannot open `/home/hacker/not-the-flag' (No such file or directory)
hacker@commands~linking-files:~$ ln -s /flag ~/not-the-flag
hacker@commands~linking-files:~$ cat /challenge/catflag
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:~$ -s
bash: -s: command not found
hacker@commands~linking-files:~$ cat -s /challenge/catflag
#!/opt/pwn.college/bash

fold -s <<< "About to read out the /home/hacker/not-the-flag file!"
cat /home/hacker/not-the-flag
hacker@commands~linking-files:~$ cat ~/not-the-flag
cat: /home/hacker/not-the-flag: Permission denied
hacker@commands~linking-files:~$ ls -l ~/not-the-flag
lrwxrwxrwx 1 hacker hacker 5 Dec 25 01:04 /home/hacker/not-the-flag -> /flag
hacker@commands~linking-files:~$ /challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{MZn7XzgSxSqZy50223Q9zwC6Z46.QX5ETN1wCOzYDN0EzW}

```

### New Learnings
Learnt the file and soft linking commands.
### References 
Info given on Linux Luminarium Modules on pwn.college


# Module Name
Linux Luminarium Module 4

## Challenge Name
Learning From Documentation

### Solve
**Flag:** `pwn.college{Q-RdUCtR5zvyNYVjv-gOVrlkGle.QX0ITO0wCOzYDN0EzW}`

I was a little confused on where to use arguments so i simply typed --giveflag after the directory of the file and i was able to find the flag.

```bash
Connected!           
hacker@man~learning-from-documentation:~$ file /challenge/challenge
/challenge/challenge: setuid executable, regular file, no read permission
hacker@man~learning-from-documentation:~$ cd /challenge
hacker@man~learning-from-documentation:/challenge$ ls -a
.  ..  .init  DESCRIPTION.md  challenge
hacker@man~learning-from-documentation:/challenge$ cd /
hacker@man~learning-from-documentation:/$ /challenge/challenge
Incorrect usage! You must pass an argument to me (read the challenge 
description for details).
hacker@man~learning-from-documentation:/$ /challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{Q-RdUCtR5zvyNYVjv-gOVrlkGle.QX0ITO0wCOzYDN0EzW}
hacker@man~learning-from-documentation:/$ 

```

### New Learnings
Revised arguments and file command.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
Learning Complex Usage

### Solve
**Flag:** `pwn.college{kocXs6BBQpi4UX3PWEp29HhJBaQ.QX1ITO0wCOzYDN0EzW}`

this was straightforward, as the example given in the description of the challenge gave the entire code except i had to replace the description.md with the /flag in order to find the flag.
```bash
Connected!           
hacker@man~learning-complex-usage:~$ /challenge/challenge
Incorrect usage! You must pass an argument to me (read the challenge 
description for details).
hacker@man~learning-complex-usage:~$ /challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{kocXs6BBQpi4UX3PWEp29HhJBaQ.QX1ITO0wCOzYDN0EzW}
hacker@man~learning-complex-usage:~$ 


```

### New Learnings
revised arguments.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
Reading Manuals

### Solve
**Flag:** `pwn.college{8Y5kmPJbu3bBTidaJ2bxKkHaps1.QX0EDO0wCOzYDN0EzW}`

on opening the manual of challenge, i noticed in the description that if u use --kmbubi NUM where NUM is 853, u get the flag, so i used it and i was able to find the flag.
```bash
Connected!           
hacker@man~reading-manuals:~$ man challenge
hacker@man~reading-manuals:~$ /challenge/challenge --kmbubi 853
Correct usage! Your flag: pwn.college{8Y5kmPJbu3bBTidaJ2bxKkHaps1.QX0EDO0wCOzYDN0EzW}
hacker@man~reading-manuals:~$ 



```

### New Learnings
learnt the man command.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
Searching Manuals

### Solve
**Flag:** `pwn.college{MTIYj9chPNZNy4huIAGkCngFc1K.QX1EDO0wCOzYDN0EzW}`

same as last challenge, except i used /flag and scrolled down till i found the right argument and then i used it to find the flag!
```bash
Connected!           
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ 
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ 
hacker@man~searching-manuals:~$ man challenge
hacker@man~searching-manuals:~$ 
hacker@man~searching-manuals:~$ /challenge/challenge --moew
Initializing...
Correct usage! Your flag: pwn.college{MTIYj9chPNZNy4huIAGkCngFc1K.QX1EDO0wCOzYDN0EzW}
hacker@man~searching-manuals:~$ 



```

### New Learnings
enhanced my skills in the man command

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
Searching For Manuals

### Solve
**Flag:** `pwn.college{82KxwGWIZ5IhmlOyRT6wpJF2bMu.QX2EDO0wCOzYDN0EzW}`
this challenge was incredibly lengthy as i tried and failed many times as i thought i had to do more than just find a singular command, however since i saw description for the -k argument, i thought of trying it and this time it worked.
```bash
Connected!           
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ 
hacker@man~searching-for-manuals:~$ man abcdsd
No manual entry for abcdsd
hacker@man~searching-for-manuals:~$ man /challenge/challenge
man: can't open /challenge/challenge: Permission denied
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -f challenge
challenge: nothing appropriate.
hacker@man~searching-for-manuals:~$ man -f flag
flag: nothing appropriate.
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man challenge -D
No manual entry for challenge
No manual entry for -D
hacker@man~searching-for-manuals:~$ man man -D
No manual entry for -D
hacker@man~searching-for-manuals:~$ man /challenge/challenge -D
man: /challenge/challenge--D: No such file or directory
man: /challenge/challenge_-D: No such file or directory
man: can't open /challenge/challenge: Permission denied
hacker@man~searching-for-manuals:~$ man /challenge/challenge -D
man: /challenge/challenge--D: No such file or directory
man: /challenge/challenge_-D: No such file or directory
man: can't open /challenge/challenge: Permission denied
hacker@man~searching-for-manuals:~$ man /challenge/challenge
man: can't open /challenge/challenge: Permission denied
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man man $MANPATH
man: man-/run/dojo/share/man:: No such file or directory
man: man_/run/dojo/share/man:: No such file or directory
man: /run/dojo/share/man:: No such file or directory
No manual entry for /run/dojo/share/man:
hacker@man~searching-for-manuals:~$ ls /run/dojo/share/ -a
.                bata24-gef  gdb                i18n       metainfo   pixmaps    tabset              xfce4
..               cmake-3.31  gedit              icons      mime       pkgconfig  terminfo            xfwm4
Thunar           code        gef                info       misc       polkit-1   themes              xml
aclocal          dbus-1      glib-2.0           iproute2   nano       qemu       vim                 xsessions
afl              doc         gsettings-schemas  jupyter    ncat       radare2    vim-plugins         zsh
applications     emacs       gtk-engines        locale     nftables   rizin      wayland-sessions
awk              fish        gtksourceview-5    ltrace     nmap       screen     wireshark
backgrounds      fonts       guile              mailutils  nvim       starship   wordlists
bash-completion  fzf         help               man        oh-my-zsh  systemd    xdg-desktop-portal
hacker@man~searching-for-manuals:~$ ls /run/dojo/share/man -a
.             da.UTF-8      es            hr            it.UTF-8  man4  pl            pt_PT      ru.UTF-8  tr.ISO8859-9
..            de            fr            hu            ja        man5  pl.ISO8859-2  ro         sk        tr.UTF-8
da            de.ISO8859-1  fr.ISO8859-1  it            man1      man7  pl.UTF-8      ru         sv        uk
da.ISO8859-1  de.UTF-8      fr.UTF-8      it.ISO8859-1  man3      man8  pt_BR         ru.KOI8-R  tr        zh
hacker@man~searching-for-manuals:~$ man ls $MANPATH
man: ls-/run/dojo/share/man:: No such file or directory
man: ls_/run/dojo/share/man:: No such file or directory
man: /run/dojo/share/man:: No such file or directory
No manual entry for /run/dojo/share/man:
hacker@man~searching-for-manuals:~$ -l /run/dojo/share/man 
bash: -l: command not found
hacker@man~searching-for-manuals:~$ -ld
bash: -ld: command not found
hacker@man~searching-for-manuals:~$ ld
/nix/store/mkvc0lnnpmi604rqsjdlv1pmhr638nbd-binutils-2.44/bin/ld: no input files
hacker@man~searching-for-manuals:~$ l
bash: l: command not found
hacker@man~searching-for-manuals:~$ ls
a  not-the-flag
hacker@man~searching-for-manuals:~$ ls -l
total 8
-rw-r--r-- 1 root   hacker 60 Nov  8 20:24 a
lrwxrwxrwx 1 hacker hacker  5 Dec 25 01:04 not-the-flag -> /flag
hacker@man~searching-for-manuals:~$ cat not-the-flag
cat: not-the-flag: Permission denied
hacker@man~searching-for-manuals:~$ cat a
pwn.college{ITnvUHTsjlgHk0S-a9yCJp6y64R.QXzMDO0wCOzYDN0EzW}
hacker@man~searching-for-manuals:~$ ^C
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man challenge -u
No manual entry for challenge
No manual entry for -u
hacker@man~searching-for-manuals:~$ man --update
What manual page do you want?
For example, try 'man man'.
hacker@man~searching-for-manuals:~$ man man --update
No manual entry for --update
hacker@man~searching-for-manuals:~$ 
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ mandb
/run/dojo/bin/mandb: warning: $MANPATH set, appending /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
/run/dojo/bin/mandb: can't chmod /var/cache/man/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/544: Permission denied
Processing manual pages under /usr/share/man...
/run/dojo/bin/mandb: can't chmod /var/cache/man/id/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/id/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/id/544: Permission denied
Processing manual pages under /usr/share/man/id...
/run/dojo/bin/mandb: can't chmod /var/cache/man/ja/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/ja/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/ja/544: Permission denied
Processing manual pages under /usr/share/man/ja...
/run/dojo/bin/mandb: can't chmod /var/cache/man/it/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/it/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/it/544: Permission denied
Processing manual pages under /usr/share/man/it...
/run/dojo/bin/mandb: can't chmod /var/cache/man/ko/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/ko/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/ko/544: Permission denied
Processing manual pages under /usr/share/man/ko...
/run/dojo/bin/mandb: can't chmod /var/cache/man/da/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/da/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/da/544: Permission denied
Processing manual pages under /usr/share/man/da...
/run/dojo/bin/mandb: can't chmod /var/cache/man/nl/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/nl/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/nl/544: Permission denied
Processing manual pages under /usr/share/man/nl...
/run/dojo/bin/mandb: can't chmod /var/cache/man/hu/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/hu/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/hu/544: Permission denied
Processing manual pages under /usr/share/man/hu...
/run/dojo/bin/mandb: can't chmod /var/cache/man/es/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/es/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/es/544: Permission denied
Processing manual pages under /usr/share/man/es...
/run/dojo/bin/mandb: can't chmod /var/cache/man/de/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/de/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/de/544: Permission denied
Processing manual pages under /usr/share/man/de...
/run/dojo/bin/mandb: can't chmod /var/cache/man/fr/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/fr/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/fr/544: Permission denied
Processing manual pages under /usr/share/man/fr...
/run/dojo/bin/mandb: can't chmod /var/cache/man/tr/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/tr/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/tr/544: Permission denied
Processing manual pages under /usr/share/man/tr...
/run/dojo/bin/mandb: can't chmod /var/cache/man/pl/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/pl/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/pl/544: Permission denied
Processing manual pages under /usr/share/man/pl...
/run/dojo/bin/mandb: can't chmod /var/cache/man/pt/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/pt/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/pt/544: Permission denied
Processing manual pages under /usr/share/man/pt...
/run/dojo/bin/mandb: can't chmod /var/cache/man/ru/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/ru/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/ru/544: Permission denied
Processing manual pages under /usr/share/man/ru...
/run/dojo/bin/mandb: can't chmod /var/cache/man/zh_TW/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/zh_TW/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/zh_TW/544: Permission denied
Processing manual pages under /usr/share/man/zh_TW...
/run/dojo/bin/mandb: can't chmod /var/cache/man/sv/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/sv/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/sv/544: Permission denied
Processing manual pages under /usr/share/man/sv...
/run/dojo/bin/mandb: can't chmod /var/cache/man/cs/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/cs/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/cs/544: Permission denied
Processing manual pages under /usr/share/man/cs...
/run/dojo/bin/mandb: can't chmod /var/cache/man/zh_CN/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/zh_CN/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/zh_CN/544: Permission denied
Processing manual pages under /usr/share/man/zh_CN...
/run/dojo/bin/mandb: can't chmod /var/cache/man/pt_BR/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/pt_BR/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/pt_BR/544: Permission denied
Processing manual pages under /usr/share/man/pt_BR...
/run/dojo/bin/mandb: can't chmod /var/cache/man/sk/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/sk/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/sk/544: Permission denied
Processing manual pages under /usr/share/man/sk...
/run/dojo/bin/mandb: can't chmod /var/cache/man/ro/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/ro/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/ro/544: Permission denied
Processing manual pages under /usr/share/man/ro...
/run/dojo/bin/mandb: can't chmod /var/cache/man/hr/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/hr/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/hr/544: Permission denied
Processing manual pages under /usr/share/man/hr...
/run/dojo/bin/mandb: can't chmod /var/cache/man/zh/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/zh/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/zh/544: Permission denied
Processing manual pages under /usr/share/man/zh...
/run/dojo/bin/mandb: can't chmod /var/cache/man/sr/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/sr/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/sr/544: Permission denied
Processing manual pages under /usr/share/man/sr...
/run/dojo/bin/mandb: can't chmod /var/cache/man/sl/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/sl/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/sl/544: Permission denied
Processing manual pages under /usr/share/man/sl...
/run/dojo/bin/mandb: can't chmod /var/cache/man/fi/CACHEDIR.TAG: Operation not permitted
/run/dojo/bin/mandb: can't remove /var/cache/man/fi/CACHEDIR.TAG: Permission denied
/run/dojo/bin/mandb: fopen /var/cache/man/fi/544: Permission denied
Processing manual pages under /usr/share/man/fi...
/run/dojo/bin/mandb: fopen /var/cache/man/oldlocal/544: Permission denied
Processing manual pages under /usr/local/man...
Processing manual pages under /nix/var/nix/profiles/default/share/man...
/run/dojo/bin/mandb: warning: cannot create catdir /var/cache/man/nixpkgs
/run/dojo/bin/mandb: can't create index cache /var/cache/man/nixpkgs/544: No such file or directory
hacker@man~searching-for-manuals:~$ sudo mandb
sudo: workspace is not privileged
hacker@man~searching-for-manuals:~$ man challenge
No manual entry for challenge
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ manpath
/run/dojo/bin/manpath: warning: $MANPATH set, appending /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
/run/dojo/share/man:/run/dojo/share/man:/usr/local/man:/usr/local/share/man:/usr/share/man
hacker@man~searching-for-manuals:~$ manpath man
manpath: Too many arguments
Try 'manpath --help' or 'manpath --usage' for more information.
hacker@man~searching-for-manuals:~$ ls ^C
hacker@man~searching-for-manuals:~$ ls /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
/run/dojo/share/man
/nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
bash: /run/dojo/share/man: Is a directory
hacker@man~searching-for-manuals:~$ ls /usr/local/share/man
man1
hacker@man~searching-for-manuals:~$ ls /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
/nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
hacker@man~searching-for-manuals:~$ /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf
bash: /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.conf: Permission denied
hacker@man~searching-for-manuals:~$ ^[[200~/nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.confls /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0
bash: /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/man_db.confls: No such file or directory
hacker@man~searching-for-manuals:~$ ~
bash: /home/hacker: Is a directory
hacker@man~searching-for-manuals:~$ /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/
bash: /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/: Is a directory
hacker@man~searching-for-manuals:~$ ls /nix/store/17a3l57c8lnfaqbxfw9f7m9wriazv5vj-man-db-2.13.0/etc/
man_db.conf
hacker@man~searching-for-manuals:~$ ls /usr/share/man
cs  de  fi  hr  id  ja  man1  man3  man5  man7  nl  pt     ro  sk  sr  tr  zh_CN
da  es  fr  hu  it  ko  man2  man4  man6  man8  pl  pt_BR  ru  sl  sv  zh  zh_TW
hacker@man~searching-for-manuals:~$ ls /usr/share/man -a
.   cs  de  fi  hr  id  ja  man1  man3  man5  man7  nl  pt     ro  sk  sr  tr  zh_CN
..  da  es  fr  hu  it  ko  man2  man4  man6  man8  pl  pt_BR  ru  sl  sv  zh  zh_TW
hacker@man~searching-for-manuals:~$ ls /usr/share/man/cs
man1  man5  man8
hacker@man~searching-for-manuals:~$ ls /usr/share/man/da
man1  man5  man8
hacker@man~searching-for-manuals:~$ ls /usr/share/man/de
man1  man5  man7  man8
hacker@man~searching-for-manuals:~$ ls /usr/share/man/ro
man1
hacker@man~searching-for-manuals:~$ ls /usr/share/man/zh_CN
man1  man5  man8
hacker@man~searching-for-manuals:~$ ls /run/dojo/share/man
da            de.ISO8859-1  fr.ISO8859-1  it            man1  man7          pl.UTF-8  ru         sv            uk
da.ISO8859-1  de.UTF-8      fr.UTF-8      it.ISO8859-1  man3  man8          pt_BR     ru.KOI8-R  tr            zh
da.UTF-8      es            hr            it.UTF-8      man4  pl            pt_PT     ru.UTF-8   tr.ISO8859-9
de            fr            hu            ja            man5  pl.ISO8859-2  ro        sk         tr.UTF-8
hacker@man~searching-for-manuals:~$ 
hacker@man~searching-for-manuals:~$ ls /run/dojo/share/man/da
man1
hacker@man~searching-for-manuals:~$ ls /run/dojo/share/man/ja
man1
hacker@man~searching-for-manuals:~$ ls /run/dojo/share/man/da.UTF-8
man1
hacker@man~searching-for-manuals:~$ MAN MAN
bash: MAN: command not found
hacker@man~searching-for-manuals:~$ man man
hacker@man~searching-for-manuals:~$ man -k challenge
xwhmlywpbu (1)       - print the flag!
hacker@man~searching-for-manuals:~$ xwhmlywpbu
bash: xwhmlywpbu: command not found
hacker@man~searching-for-manuals:~$ man xwhmlypbu
No manual entry for xwhmlypbu
hacker@man~searching-for-manuals:~$ man xwhmlywpbu
hacker@man~searching-for-manuals:~$ challenge --xwhmly
bash: challenge: command not found
hacker@man~searching-for-manuals:~$ man xwhmlywpbu
hacker@man~searching-for-manuals:~$ /challenge/challenge --xwhmly 825
Correct usage! Your flag: pwn.college{82KxwGWIZ5IhmlOyRT6wpJF2bMu.QX2EDO0wCOzYDN0EzW}
hacker@man~searching-for-manuals:~$ 

```

### New Learnings
enhanced my skills in the man command.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
Helpful Programs

### Solve
**Flag:** `pwn.college{wxgKoT4l7Yj53SQaw4nLFXN7vZu.QX3IDO0wCOzYDN0EzW}`

i already had gotten the way to solve the problem at first, but i overlooked the -p argument and i was messing around till i reread the description of the help instructions, after which it was straightforward, i found the secret integer value required and then used -g with the secret value, and the challenge script worked out and i was able to get the flag!
```bash
Connected!           
hacker@man~helpful-programs:~$ /challenge/challenge
No options specified.
hacker@man~helpful-programs:~$ /challenge/challenge --help
usage: a challenge to make you ask for help [-h]
                                            [--fortune]
                                            [-v]
                                            [-g GIVE_THE_FLAG]
                                            [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct
                        value
  -p, --print-value     print the value that will cause the
                        -g option to give you the flag
hacker@man~helpful-programs:~$ /challenge/challenge -g GIVE_THE_FLAG
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]
a challenge to make you ask for help: error: argument -g/--give-the-flag: invalid int value: 'GIVE_THE_FLAG'
hacker@man~helpful-programs:~$ man challenge
No manual entry for challenge
hacker@man~helpful-programs:~$ man /challenge/challenge
/run/dojo/bin/man: can't open /challenge/challenge: Permission denied
hacker@man~helpful-programs:~$ man challenge -k
No manual entry for challenge
No manual entry for -k
hacker@man~helpful-programs:~$ man -k challenge
challenge: nothing appropriate.
hacker@man~helpful-programs:~$ /challenge/challenge -p
The secret value is: 475
hacker@man~helpful-programs:~$ /challenge/challenge -g 475
Correct usage! Your flag: pwn.college{wxgKoT4l7Yj53SQaw4nLFXN7vZu.QX3IDO0wCOzYDN0EzW}
hacker@man~helpful-programs:~$ 

```

### New Learnings
learnt the help argument.

### References 
Info given on Linux Luminarium Modules on pwn.college

## Challenge Name
Helpful for Builtins

### Solve
**Flag:** `pwn.college{YmV887gbiY40o0qiVOosQH_IZZL.QX0ETO0wCOzYDN0EzW}`

This was also a very straightforward challenge, it was a bit off-putting till i realized that now challenge is a command in itself and i don't have to type /challenge/challenge to run the flag script, so all i had to do was prefix it with help and get all the instructions needed, in order to find the flag, which i was able to!
```bash
                                                                                                                      Connected!           
hacker@man~help-for-builtins:~$ help /challenge/challenge
bash: help: no help topics match `/challenge/challenge'.  Try `help help' or `man -k /challenge/challenge' or `info /challenge/challenge'.
hacker@man~help-for-builtins:~$ help challenge
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune		display a fortune
      --version		display the version
      --secret VALUE	prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "YmV887gb".
hacker@man~help-for-builtins:~$ challenge --secret YmV887gb
Correct! Here is your flag!
pwn.college{YmV887gbiY40o0qiVOosQH_IZZL.QX0ETO0wCOzYDN0EzW}

```

### New Learnings
learnt the help command used for bulletins.

### References 
Info given on Linux Luminarium Modules on pwn.college