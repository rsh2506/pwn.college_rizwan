# Untangling Users

## Becoming root with su

In this challenge, we will cover the older one, su (the substitute user command). This is not typically used to elevate to root access anymore, but it is an elegant utility from a more civilized time, and we'll cover it first.

### Solve
**Flag:** pwn.college{AqDDJnLiF6xo84Fj54sDxeqf2If.QX1UDN1wiM5AzNzEzW}
 

```bash
su
password: hack-the-planet
ls
cat not-the-flag
pwn.college{AqDDJnLiF6xo84Fj54sDxeqf2If.QX1UDN1wiM5AzNzEzW}
```

### New Learnings
`su` command to get root (administrative) access of your system


## Other users with su

With no arguments, su will start a root shell (after authenticating with root's password). However, you can also give a username as an argument to switch to that user instead of root.

### Solve
**Flag:** pwn.college{k_69rOoYBsfLum-fd2DOhIFxhbG.QX2UDN1wiM5AzNzEzW}

```bash
su zardus
Password: dont-hack-me
/challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{k_69rOoYBsfLum-fd2DOhIFxhbG.QX2UDN1wiM5AzNzEzW}
```

### New learnings
giving username argument with `su` to switch to that user. 


## Cracking passwords

in this challenge we will learn about decrypting passwords using john command.

### Solve
**FLAG:** pwn.college{cDwdJWiwWp0uQaQRUb9ECMOqP_n.QX3UDN1wiM5AzNzEzW}

```bash
cd /challenge/shadow-leak
john shadow-leak
john shadow-leak --show
hacker:NO PASSWORD:20357:0:99999:7:::
zardus:aardvark:20371:0:99999:7:::
2 password hashes cracked, 0 left
su zardus
Password: aardvark
/challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{cDwdJWiwWp0uQaQRUb9ECMOqP_n.QX3UDN1wiM5AzNzEzW}
```

### New learnings
i can now crack encrypted passwords.

## Using `sudo`

in this challenge we will learn about `sudo` command to gain system-wide access to files and directories.

### Solve

**Flag:** pwn.college{U1w6sCJEUhaJXBwUTwIGT68egSU.QX4UDN1wiM5AzNzEzW}

```bash
ls
cat not-the-flag
cat: not-the-flag: Permission denied
sudo cat not-the-flag
pwn.college{U1w6sCJEUhaJXBwUTwIGT68egSU.QX4UDN1wiM5AzNzEzW}
```
### New learnings
i can now use `sudo` for system admistration.
















