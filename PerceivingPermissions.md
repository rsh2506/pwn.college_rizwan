# Perceiving Permissions

## Changing File Ownership

In this level, we will practice changing the owner of the /flag file to the hacker user, and then read the flag. For this challenge only, I made it so that you can use chown to your heart's content as the hacker user (again, typically, this requires you to be root).

### Solve
**Flag:** pwn.college{4r5jMnQbKXVM0G9wSPOjrI7juC5.0VN4IDOxwiM5AzNzEzW}
 

```bash
cd /
chown hacker flag
cat flag
pwn.college{MrhEXn7eQEfLth1W5tTuSvwVumK.QXxEjN0wiM5AzNzEzW}
```

### New learnings
i can now change file ownership for various files.

## Groups and Files

in this challenge we will how to change group ownership for a file

### Solve
**Flag:** pwn.college{8WfQtOkGcQN1UTPZ5PVb7KsaUcZ.QXxcjM1wiM5AzNzEzW}

```bash
id
uid=1000(hacker) gid=1000(hacker) groups=1000(hacker)
cd /
ls -l flag
-r--r----- 1 root root 60 Oct 10 18:07 flag
chgrp hacker flag
cat flag
pwn.college{8WfQtOkGcQN1UTPZ5PVb7KsaUcZ.QXxcjM1wiM5AzNzEzW}
```

### New learnings
i can now change group ownership of files using `chgrp` command.


## Fun With Groups Names

in this challenge we will check the group name using `id` and then change group ownership to the required group

### Solve
**FLAG:** pwn.college{8vkdznuouVce2WHKr25XNbDLab6.QXycjM1wiM5AzNzEzW}

```bash
cd /
cat flag
cat: flag: Permission denied
id
uid=1000(hacker) gid=1000(grp28448) groups=1000(grp28448)
chgrp grp28448 flag
cat flag
pwn.college{8vkdznuouVce2WHKr25XNbDLab6.QXycjM1wiM5AzNzEzW}
```

### New learnings
proficiency in using `id` and `chgrp`

## Changing Permissions

in this challenge we will learn about changing file permissions.

### Solve

**Flag:** pwn.college{g3AvNR43_zC1ia3xDbJO70hbx-8.QXzcjM1wiM5AzNzEzW}

```bash
cd /
cat flag
cat: flag: Permission denied
ls -l flag
-r-------- 1 root root 60 Oct 10 18:27 flag
chmod a+r
cat flag
pwn.college{g3AvNR43_zC1ia3xDbJO70hbx-8.QXzcjM1wiM5AzNzEzW}
```
### New learnings
i can now change file permissions.

## Executable Files

in this challenge we will learn to change executable permissions for an executable file

### Solve
**Flag:** pwn.college{Y6RxtIp0J3b04DBU9LPwhLPLRrh.QXyEjN0wiM5AzNzEzW}

```bash
cd /
chmod a+x /challenge/run
/challenge/run
Successful execution! Here is your flag:
pwn.college{Y6RxtIp0J3b04DBU9LPwhLPLRrh.QXyEjN0wiM5AzNzEzW}
```

### New learnings
using `chmod` to change permissions for executables

## Permission tweaking practice

8 rounds of `chmod` for practice

### Solve
**Flag:** pwn.college{84jBeeXFdFJl5Bgza5xQl3c3NEF.QXwEjN0wiM5AzNzEzW}
solved all 8 rounds successfully, then for the final part i set the flag permissions to `a+rwx`(all perms) and read the file.

### New learnings
proficiency in `chmod`

## Permissions Setting Practice
similar to previous challenge, but instead we'll use `=` instead of `+,-` to set permission parameters.

### Solve
**Flag:** pwn.college{4en7chY3u-eNtPllzr3OdlMUiUy.QXzETO0wiM5AzNzEzW}
similar to previous problem we'll solve 8 rounds of `chmod`.

### New learnings
proficiency in `chmod`

## The SUID Bit

in this challenge, we will execute programs with SUID permission. The "Set User ID" (SUID) permissions bit allows the user to run a program as the owner of that program's file.

### Solve
**Flag:** pwn.college{wczU_TBGJx02usSszbZuYV3ua19.QXzEjN0wiM5AzNzEzW}

```bash
chmod a+s /challenge/getroot
/challenge/getroot
SUCCESS! You have set the suid bit on this program, and it is running as root!
Here is your shell...
cat /flag
pwn.college{wczU_TBGJx02usSszbZuYV3ua19.QXzEjN0wiM5AzNzEzW}
```

### New learnings
i can now add `+s` permissions to files such that the program becomes executable with SUID.
















