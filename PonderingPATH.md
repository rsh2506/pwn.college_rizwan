# Pondering PATH

## The PATH variable

In this level, we will disrupt the operation of the /challenge/run program. This program will DELETE the flag file using the rm command. However, if it can't find the rm command, the flag will not be deleted, and the challenge will give it to you! Thus, you must make it so that /challenge/run also can't find the rm command.
### Solve
**Flag:** pwn.college{Idr2TYWG7kbO6hjJ-k0ArQMNHUl.QX2cDM1wiM5AzNzEzW}
 

```bash
mkdir -p /tmp/empty
export PATH=/tmp/empty
/challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: command not found
The flag is still there! I might as well give it to you!
pwn.college{Idr2TYWG7kbO6hjJ-k0ArQMNHUl.QX2cDM1wiM5AzNzEzW}
```

### New Learnings
PATH command to redirect shell command directories

## Setting PATH

in this level's /challenge/run will run the win command via its bare name, but this command exists in the /challenge/more_commands/ directory, which is not initially in the PATH. The win command is the only thing that /challenge/run needs, so you can just overwrite PATH with that one directory.

### Solve
**Flag:** pwn.college{MROsz-s3QnPUMB6my1B-D3eEn1R.QX1cjM1wiM5AzNzEzW}

```bash
cd /
export PATH=/challenge/more_commands/[CTRL+A, D]
/challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{MROsz-s3QnPUMB6my1B-D3eEn1R.QX1cjM1wiM5AzNzEzW}
```

### New learnings
i can now set PATH to different directories


## Finding Commands

In this challenge, we added a win command somewhere in your $PATH, but it won't give you the flag. Instead, it's in the same directory as a flag file that we made readable by you! You must find win (with the which command), and cat the flag out of that directory.

### Solve
**FLAG:** pwn.college{0T5JlyUUKEafa1SKrj70VBOw49G.01NzEzNxwiM5AzNzEzW}

```bash
which win
/challenge/paths/22099/win 
cd /challenge/paths/22099
cat flag
pwn.college{0T5JlyUUKEafa1SKrj70VBOw49G.01NzEzNxwiM5AzNzEzW}
```

### New learnings
i can now find commands using `which` command

## Adding Commands

in this challenge we will learn to make a shell script and add its location to the PATH

### Solve

**Flag:** pwn.college{0MigQ3u33x220twIG63JaChZJAs.QX2cjM1wiM5AzNzEzW}

```bash
mkdir /tmp/mybin
cat > /tmp/mybin/win <<'EOF'
/bin/cat /flag
EOF
chmod +x /tmp/mybin/win
export PATH=/tmp/mybin
/challenge/run
Invoking 'win'....
pwn.college{0MigQ3u33x220twIG63JaChZJAs.QX2cjM1wiM5AzNzEzW}
```
### New learnings
i can now make shell scripts, add it to PATH to invoke commands.

## Hijacking Commands

Armed with your knowledge, you can now carry out some shenanigans. This challenge is almost the same as the first challenge in this module. Again, this challenge will delete the flag using the rm command. But unlike before, it will not print anything out for you.

How can you solve this? You know that rm is searched for in the directories listed in the PATH variable. You have experience creating the win command when the previous challenge needed it. 

### Solve
**Flag:** pwn.college{spy5tcxo7l3BIE8jf5lGF6PZtL6.QX3cjM1wiM5AzNzEzW}

i created the `rm` command such that it reads out the flag itself, then set `PATH` environment to where that `rm` command is

```bash
mkdir -p /tmp/mybin
cat > /tmp/mybin/rm <<'SH'
/bin/cat /flag
exit 0
SH
chmod +x /tmp/mybin/rm
export PATH=/tmp/mybin:$PATH
/challenge/run
Trying to remove /flag...
Found 'rm' command at /tmp/mybin/rm. Executing!
pwn.college{spy5tcxo7l3BIE8jf5lGF6PZtL6.QX3cjM1wiM5AzNzEzW}
```

### New learnings
proficiency in creating commands and setting `PATH` environment for it