# Chaining commands

## Chaining with semicolons

Give it a try now! In this level,
you must run /challenge/pwn and then /challenge/college, chaining them with a semicolon.

### Solve
**Flag:** pwn.college{Uzr4sCG1q3j_mmjkKXnLqCAIURL.QX1UDO0wiM5AzNzEzW}

chaining /challenge/pwn and /challenge/college with semi-colon as /challenge/pwn ; /challenge/college

```bash
/challenge/pwn ; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{Uzr4sCG1q3j_mmjkKXnLqCAIURL.QX1UDO0wiM5AzNzEzW}
```

### New Learnings
chaining two commands into a single line using semi-colon.


## Building on Success

In this challenge, you need to chain the programs /challenge/first-success and 
/challenge/second using the && operator.

### Solve
**Flag:** pwn.college{wB-qG3CO06R10-SdINS_q2YVNyN.0lM0MDOxwiM5AzNzEzW}

chaining /challenge/first-success and /challenge/second using && as /challenge/first-success && /challenge/second


```bash
/challenge/first-success
/challenge/second

Error: /challenge/first-success must be successfully chained with
/challenge/second using &&

/challenge/first-success && /challenge/second

Nice chaining! Flag: pwn.college{wB-qG3CO06R10-SdINS_q2YVNyN.0lM0MDOxwiM5AzNzEzW}
```

### New Learnings
chaining programs using && operator . second program will only run when the first program executes successfully. 


## Handling failure

In this challenge, you need to chain /challenge/first-failure and /challenge/second using the || operator. Go for it!

### Solve
**Flag:**  pwn.college{4dbOK4ZWc79hvjTEXCjN-GzMO5o.01M0MDOxwiM5AzNzEzW}

chained the /challenge/first-failure with /challenge/second as 
/challenge/first-failure || /challenge/second


```bash
/challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{4dbOK4ZWc79hvjTEXCjN-GzMO5o.01M0MDOxwiM5AzNzEzW}
```

### New Learnings
chaining two programs with || operator works only if the first command fails.


## Your first shell script

Same as last level, run /challenge/pwn and then /challenge/college,
but this time in a shell script called x.sh, then run it with bash!

### Solve
**Flag:**  pwn.college{80hosJtNrC3Fzho_jVjoHNC7kUT.QXxcDO0wiM5AzNzEzW}

```bash
echo "/challenge/pwn; /challenge/college" > x.sh
bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{80hosJtNrC3Fzho_jVjoHNC7kUT.QXxcDO0wiM5AzNzEzW}
```

### New Learnings
i can now develop shell scripts.

## Redirecting script output

In this level, we will practice piping (|) from your script to another program. Like before, you need to create a script that calls the /challenge/pwn command followed by the /challenge/college command, and pipe the output of the script into a single invocation of the /challenge/solve command!

### Solve
**Flag:** pwn.college{QceAAogf6SYPWdbGrBaJ8F8O6Xo.QX4ETO0wiM5AzNzEzW}

```bash
echo "/challenge/pwn; /challenge/college" > x.sh
bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{QceAAogf6SYPWdbGrBaJ8F8O6Xo.QX4ETO0wiM5AzNzEzW}
```

### New Learnings
I can now use piping to redirect outputs of a script to another command.

## Executable shell scripts

Make a shellscript that will invoke /challenge/solve, make it executable, and run it without explicitly invoking bash

### Solve
**Flag:** pwn.college{033y_OrJtGmEBTBZ3dDn1PWBnnQ.QX0cjM1wiM5AzNzEzW}
```bash
echo "/challenge/solve" > flag.sh
chmod +x flag.sh
./flag.sh
Congratulations on your shell script execution! Your flag:
pwn.college{033y_OrJtGmEBTBZ3dDn1PWBnnQ.QX0cjM1wiM5AzNzEzW}
```

### New Learnings
I can now run shell scripts as executables without the need of `bash`.
