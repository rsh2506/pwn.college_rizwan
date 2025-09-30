# Digesting Documentation

## Learning from documentation

The program for this challenge is /challenge/challenge, and you'll need to invoke it properly in order for it to give you the flag.
Let's pretend that this is its documentation

### Solve
**Flag:** pwn.college{4x9vbdDgSIq9hfHScViNA_VLN9T.QX0ITO0wiM5AzNzEzW}

passed --giveflag argument on /challenge/challenge  

```bash
/challenge/challenge --giveflag
Correct argument! Here is your flag:
pwn.college{4x9vbdDgSIq9hfHScViNA_VLN9T.QX0ITO0wiM5AzNzEzW}
```

### New Learnings
program and argument.


## Learning complex usage

/challenge/challenge program allows you to print arbitrary files to the terminal,
when given the --printfile argument. The argument to the --printfile argument is the path of the flag to read. For example,
/challenge/challenge --printfile /challenge/DESCRIPTION.md will print out the description of the level!

### Solve
**Flag:** pwn.college{AbJizBZveWaYDGt8JDvJ7srsNzq.QX1ITO0wiM5AzNzEzW}

passed printfile argument on /challenge/challenge to get value of /flag. 

```bash
/challenge/challenge --printfile /flag
Correct argument! Here is the /flag file:
pwn.college{AbJizBZveWaYDGt8JDvJ7srsNzq.QX1ITO0wiM5AzNzEzW}
```

### New Learnings
program and argument with file to read.


## Reading manuals

The challenge in this level has a secret option that, when you use it, will cause the challenge to print the flag. You must learn this option through the man page for challenge!

### Solve
**Flag:** pwn.college{crP43cZVAD-s6agVBV3etUGc5OZ.QX0EDO0wiM5AzNzEzW}

Read the challenge manual using man challenge then /challenge/challenge --sxgbit 846.

```bash
man challenge
/challenge/challenge --sxgbit 846
Correct usage! Your flag: pwn.college{crP43cZVAD-s6agVBV3etUGc5OZ.QX0EDO0wiM5AzNzEzW}
```

### New Learnings
man command to read a manpage.


## Searching manuals

Find the option that will give you the flag by reading the challenge man page.

### Solve
**Flag:** pwn.college{UwIc7BIlPQ6U1Hm8gt2n1gCiPa3.QX1EDO0wiM5AzNzEzW}

Read the challenge manual searched /flag i found --pmy argument which gave the flag.

```bash
man challenge
/challenge/challenge --pmy
Initializing...
Correct usage! Your flag: pwn.college{UwIc7BIlPQ6U1Hm8gt2n1gCiPa3.QX1EDO0wiM5AzNzEzW}
```

### New Learnings
Searching in a manual using / command inside manpage.


## Searching for manuals

Find the hidden manpage and read it to get the flag.

### Solve
**Flag:** pwn.college{Uku-SjYhT-XWkWKgAo34q3n0dKK.QX2EDO0wiM5AzNzEzW}

First read the man man manpage in which i found about about apropos then used it to search for challenge manpage using man -k challenge then read the challenge manpage followed instruction , got the flag.

```bash
man man
man -k challenge
zuklfjfgzb (1)       - print the flag!
man zuklfjfgzb
/challenge/challenge --zuklfj 343
Correct usage! Your flag: pwn.college{Uku-SjYhT-XWkWKgAo34q3n0dKK.QX2EDO0wiM5AzNzEzW}
```

### New Learnings
man -k apropos search tool ,Search the short manual page descriptions for keywords and display any matches.


## Helpful programs

In this level, you will practice reading a program's documentation with --help. 

### Solve
**Flag:** pwn.college{seCAddJ6H6TyQV74QazLzO9W7S-.QX3IDO0wiM5AzNzEzW}

Read challenge program's help documentation used arguments correctly , got the flag.

```bash
/challenge/challenge -h
/challenge/challenge --fortune
The solution to a problem changes the nature of the problem.
                -- Peer
/challenge/challenge -v
I'm exactly the version I need to be!
/challenge/challenge -p
The secret value is: 432
/challenge/challenge -g 432
Correct usage! Your flag: pwn.college{seCAddJ6H6TyQV74QazLzO9W7S-.QX3IDO0wiM5AzNzEzW}
```

### New Learnings
read the programs's documentation using -h or --help.


## Help for Builtins

This challenge's challenge command is a shell builtin, rather than a program. Like before, you need to lookup its help to figure out the secret value to pass to it!

### Solve
**Flag:** pwn.college{wB04u-Hgzv-fFEYs5B0jkEcpCmV.QX0ETO0wiM5AzNzEzW}

Read the challenge manual searched /flag i found --pmy argument which gave the flag.

```bash
help challenge
/challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!

    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "oepyuInb".

challenge --fortune
I think I'm schizophrenic.  One half of me's paranoid and the other half's
out to get him.
challenge --version
I'm exactly the version I need to be!
challenge --secret oepyuInb
Correct! Here is your flag!
pwn.collegepwn.college{wB04u-Hgzv-fFEYs5B0jkEcpCmV.QX0ETO0wiM5AzNzEzW}
```

### New Learnings
Builtin command help. Gives list of shell builtins by running the builtin help.i can get help on a specific command using builtin help.














