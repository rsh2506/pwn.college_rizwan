# comprehending commands 

## cat: not the pet , but the command! 

read the flag copied in the flag file in my home directory read it with cat.

### Solve
**Flag:** pwn.college{o-rK7etgbbo3ENWeB98F8Gns0vM.QXxcTN0wiM5AzNzEzW}

read flag using cat  

```bash
cat flag
pwn.college{o-rK7etgbbo3ENWeB98F8Gns0vM.QXxcTN0wiM5AzNzEzW}}
```

### New Learnings
cat command.  


## Catting absolute paths

access the flag by using cat command by its absolute path /flag.

### Solve
**Flag:** pwn.college{MwyM5g6zy69EzKiKRdEdlkCH4Dc.QX5ETO0wiM5AzNzEzW}  

read flag by absolte path /flag using cat  

```bash
cat /flag
pwn.college{MwyM5g6zy69EzKiKRdEdlkCH4Dc.QX5ETO0wiM5AzNzEzW}  
```

### New Learnings
read flag by absolute path using cat.  


## more catting practice

access the flag by using cat command by its absolute path in different directory no 'cd' and 'cat flag'.

### Solve
**Flag:** pwn.college{QkZYpel-2xtJ54Dk4GOH61Xakiz.QXwITO0wiM5AzNzEzW}   

read flag using cat flag from /lib/emacsen-common/flag.

```bash
cat /lib/emacsen-common/flag
pwn.college{QkZYpel-2xtJ54Dk4GOH61Xakiz.QXwITO0wiM5AzNzEzW}   
```

### New Learnings
read flag by absolute path from different directory without changing current directory using cat.


## grepping for a needle in a haystack

access the flag from a large file using grep command. 

### Solve
**Flag:** pwn.college{gxm0nIrqQ7M_Q-Ps4N3bOO_zOue.QX3EDO0wiM5AzNzEzW}    

find flag using grep 

```bash
grep pwn.college /challenge/data.txt
pwn.college{gxm0nIrqQ7M_Q-Ps4N3bOO_zOue.QX3EDO0wiM5AzNzEzW}    
```

### New Learnings
grep command used for searching contents we need in a large file.


## comparing files

access the flag by comparing two files one has fake flags other has real. 

### Solve
**Flag:** > pwn.college{QRbxfVEW67o3REqX48QlDHaGKIW.01MwMDOxwiM5AzNzEzW}

compare file1 by file2 using diff.

```bash
diff /challenge/decoys_only.txt /challenge/decoys_and_real.txt
84a85
> pwn.college{QRbxfVEW67o3REqX48QlDHaGKIW.01MwMDOxwiM5AzNzEzW}
```

### New Learnings
diff command used for find difference in 2 files. 


## listing files

In this challenge, we've named /challenge/run with some random name! 
List the files in /challenge to find it.

### Solve
**Flag:** > pwn.college{MguzRpDraC_67e5Uy0HNpmZelqn.QX4IDO0wiM5AzNzEzW}

listed files in /challenge then accesed the renamed flag file.

```bash
ls /challenge
2000-renamed-run-9548  DESCRIPTION.md
/challenge/2000-renamed-run-9548
Yahaha, you found me! Here is your flag:
pwn.college{MguzRpDraC_67e5Uy0HNpmZelqn.QX4IDO0wiM5AzNzEzW}
```

### New Learnings
I can list all files under a directory using ls command. 


## touching files

In this level, please create two files: /tmp/pwn and /tmp/college,
and run /challenge/run to get your flag!.

### Solve
**Flag:** > pwn.college{kCLl7B6WAuxQzJ12qSxxFt3_GzG.QXwMDO0wiM5AzNzEzW}

created two files pwn and college then used /challenge/run to get the flag.

```bash
cd /tmp
touch pwn
touch college
ls
bin  college  hsperfdata_root  pwn  tmp.TpSOPGOVKK
/challenge/run
Success! Here is your flag:
pwn.college{kCLl7B6WAuxQzJ12qSxxFt3_GzG.QXwMDO0wiM5AzNzEzW}
```

### New Learnings
I can create a file in a directory using touch command.


## removing files

this challenge will create a delete_me file in your home directory! Delete it, 
then run /challenge/check, 
which will make sure you've deleted it and then give you the flag!.

### Solve
**Flag:** > pwn.college{gO5c2l2UFmVhS8ykFoHK8XNJfo-.QX2kDM1wiM5AzNzEzW}

deleted a file using rm .

```bash
ls
delete_met
rm delete_me
/challenge/check
Excellent removal. Here is your reward:
pwn.college{gO5c2l2UFmVhS8ykFoHK8XNJfo-.QX2kDM1wiM5AzNzEzW}
```

### New Learnings
I can delete a file in a directory using rm command.


## moving files

This challenge wants you to move the /flag file into /tmp/hack-the-planet (do it)!
When you're done,
run /challenge/check, which will check things out and give the flag to you.

### Solve
**Flag:** pwn.college{0vnE4JHtXHMcH9y2YPZUII7sj3Z.0VOxEzNxwiM5AzNzEzW}

moved /flag to /tmp/hack-the-planet then run /challenge/check to get the flag.

```bash
cd /tmp
mv /flag /tmp/hack-the-planet
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
/challenge/check
Congrats! You successfully moved the flag to /tmp/hack-the-planet! Here it is:
pwn.college{0vnE4JHtXHMcH9y2YPZUII7sj3Z.0VOxEzNxwiM5AzNzEzW}
```

### New Learnings
I can move a file in a directory using mv command.


## hidden files

find the flag, hidden as a dot-prepended file in /.

### Solve
**Flag:** pwn.college{Q0g0GgKTkTbCKDxy5xf6EdA_-2l.QXwUDO0wiM5AzNzEzW}

moved /flag to /tmp/hack-the-planet then run /challenge/check to get the flag.

```bash
cd /
ls -a
Correct! Performing 'mv /flag /tmp/hack-the-planet'.
ls -a
.           .flag-293013016824097  challenge  home   lib64   mnt  proc  sbin  tmp
..          bin                    dev        lib    libx32  nix  root  srv   usr
.dockerenv  boot                   etc        lib32  media   opt  run   sys   var
cat .flag-293013016824097
pwn.college{Q0g0GgKTkTbCKDxy5xf6EdA_-2l.QXwUDO0wiM5AzNzEzW}
```

### New Learnings
I can list a 'dot file' that starts with '.' using '-a' flag with 'ls' command as 'ls -a'.


## An epic filesystem quest 

In this challenge, I have hidden the flag! Here, 
you will use ls and cat to follow my breadcrumbs and find it!

### Solve
**Flag:** pwn.college{wXAbei-RV1NDlnFuo4MVDqAZJlr.QX5IDO0wiM5AzNzEzW}

moved /flag to /tmp/hack-the-planet then run /challenge/check to get the flag.

```bash
cd /
ls
.           BRIEF  challenge  flag  lib32   media  opt   run   sys  var
..          bin    dev        home  lib64   mnt    proc  sbin  tmp
.dockerenv  boot   etc        lib   libx32  nix    root  srv   usr
cat BRIEF
Congratulations, you found the clue!
The next clue is in: /opt/linux/linux-5.4/drivers/s390/cio

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.
.
.
.
.
.
.
.
.
cat /usr/lib/debug/.build-id/f8/BLUEPRINT-TRAPPED
CONGRATULATIONS! Your perserverence has paid off, and you have found the flag!
It is: pwn.college{wXAbei-RV1NDlnFuo4MVDqAZJlr.QX5IDO0wiM5AzNzEzW}

```

### New Learnings
practice of 'cd' , 'cat' , 'ls' , 'ls-a'.

## making directories

create a /tmp/pwn directory and make a college file in it! Then run /challenge/run.

### Solve
**Flag:** pwn.college{cWNV-HT7knVTPWRXPMvQC3iLPS0.QXxMDO0wiM5AzNzEzW}

changed directory to /tmp then created a pwn directory using 
'mkdir' command then changed directory to /tmp/pwn then created a 'college' file using 'touch' command.

```bash
cd /tmp
mkdir pwn
touch college
/challenge/run
Success! Here is your flag:
pwn.college{cWNV-HT7knVTPWRXPMvQC3iLPS0.QXxMDO0wiM5AzNzEzW}
```

### New Learnings
I can create a dircectory using 'mkdir' command.


## finding files

The flag is hidden in a random directory on the filesystem. It's still called flag. Go find it!

### Solve
**Flag:** pwn.college{c-CmwBc1sq_DpluPxoa-YSlkKrs.QXyMDO0wiM5AzNzEzW}

search the filesystem for flag using find command 

```bash
find / -name flag

/usr/lib/jvm/java-17-openjdk-amd64/legal/java.security.jgss/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
.
.
.
.
/nix/store/dz2qxywk6d8hc1gkarpwbhyxb50sh2ak-pwntools-4.14.0/lib/python3.13/site-packages/pwnlib/flag

cat /usr/lib/jvm/java-17-openjdk-amd64/legal/java.security.jgss/flag
pwn.college{c-CmwBc1sq_DpluPxoa-YSlkKrs.QXyMDO0wiM5AzNzEzW}
```

### New Learnings
i can search any directory using 'find' command.

## linking files
use a symlink to read /flag via /challenge/catflag

### Solve
**Flag:** pwn.college{cCAZXaiu5ysC6blfYb877VvSdSJ.QX5ETN1wiM5AzNzEzW}

first delete the stored file in /home/hacker/not-the-flag, then create a symlink for /flag in /home/hacker/not-the-flag, so that the /catflag programs reads the flag instead

```bash
rm /home/hacker/not-the-flag
ln -s /flag /home/hacker/not-the-flag
/challenge/catflag
About to read out the /home/hacker/not-the-flag file!
pwn.college{cCAZXaiu5ysC6blfYb877VvSdSJ.QX5ETN1wiM5AzNzEzW}
```
### New Learnings
i can now create symlinks



















