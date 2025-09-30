# Shell Variables

## Printing variables

Have your shell print out the FLAG variable and solve this challenge!

### Solve
**Flag:** pwn.college{ce9uZm6x2QDC3N5bhN_14JYc6Ta.QX3UTN0wiM5AzNzEzW} 

print FLAG variable using '$' using echo command as echo $FLAG.

```bash
echo $FLAG
pwn.college{ce9uZm6x2QDC3N5bhN_14JYc6Ta.QX3UTN0wiM5AzNzEzW} 
```

### New Learnings
I can print variables by prepending a name with a $.


## Setting variables

To solve this level, you must set the PWN variable to the value COLLEGE.
Be careful: both the names and values of variables are case-sensitive! 
PWN is not the same as pwn and COLLEGE is not the same as College.

### Solve
**Flag:** pwn.college{4lkySbQcyY9VeudlJevz7st1IPW.QX5UTN0wiM5AzNzEzW} 

set value COLLEGE to the variable PWN as PWN=COLLEGE.

```bash
PWN=COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{4lkySbQcyY9VeudlJevz7st1IPW.QX5UTN0wiM5AzNzEzW} 
```

### New Learnings
I can set a value to a variable.


## Multi-word variables

In this level, you'll need to set the variable PWN to COLLEGE YEAH. Good luck!

### Solve
**Flag:** pwn.college{8hpR7ftfSQfdWm8rO5BJCx7piB2.QXwYTN0wiM5AzNzEzW} 

set value COLLEGE YEAH to the variable PWN using quotaion as PWN="COLLEGE YEAH".

```bash
PWN="COLLEGE YEAH"
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{8hpR7ftfSQfdWm8rO5BJCx7piB2.QXwYTN0wiM5AzNzEzW} 
```

### New Learnings
I can set a value with spaces to the variable by quoting the value with " " .


## Exporting variables

In this challenge, you must invoke /challenge/run with the PWN variable exported and set to the value COLLEGE, 
and the COLLEGE variable set to the value PWN but not exported (e.g., not inherited by /challenge/run). Good luck!

### Solve
**Flag:** pwn.college{4nlX2-erNx6VFgz5kHSL_h4aS3Z.QXyYTN0wiM5AzNzEzW}

set value PWN to variable COLLEGE then set value COLLEGE to variable PWN export PWN then run /challenge/run .

```bash
COLLEGE=PWN
You've set the COLLEGE variable to the proper value!
PWN=COLLEGE
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
export PWN
You've set the PWN variable to the proper value!
You've set the COLLEGE variable to the proper value!
/challenge/run
CORRECT!
You have exported PWN=COLLEGE and set, but not exported, COLLEGE=PWN. Great
job! Here is your flag:
pwn.college{4nlX2-erNx6VFgz5kHSL_h4aS3Z.QXyYTN0wiM5AzNzEzW}
```

### New Learnings
export command , minimal shell implementation that is invoked as a child of the main shell process.


## Printing exported variables

Try the env command: it'll print out every exported variable set in your shell,
and you can look through that output to find the FLAG variable!

### Solve
**Flag:** pwn.college{UZ7g6Qj2FALGbuIMt_R8QT2fLu3.QX4UTN0wiM5AzNzEzW} 

run env it prints all the exported variable set in the shell.

```bash
env
SHELL=/run/dojo/bin/bash
HOSTNAME=variables~printing-exported-variables
.
.
.
FLAG=pwn.college{UZ7g6Qj2FALGbuIMt_R8QT2fLu3.QX4UTN0wiM5AzNzEzW} 
.
.
.
PATH=/run/challenge/bin:/run/dojo/bin:/root/.cargo/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
DEBIAN_FRONTEND=noninteractive
_=/run/dojo/bin/env
```

### New Learnings
env command prints all the exported variables set in the shell.


## Storing command output

Read the output of the /challenge/run command directly into a variable called PWN,
and it will contain the flag!

### Solve
**Flag:** pwn.college{YNZdcg2jZAVeYaaFsy4q1TDJb8l.QX1cDN1wiM5AzNzEzW} 

set the value of /challenge/run to the variable PWN as PWN=$(/challenge/run).
Now PWN variable stores the output of /challenge/run as a value
and when called as echo "$PWN "it will print the output of /challenge/run

```bash
PWN=$(/challenge/run)
Congratulations! You have read the flag into the PWN variable. Now print it out
and submit it!
echo $PWN
pwn.college{YNZdcg2jZAVeYaaFsy4q1TDJb8l.QX1cDN1wiM5AzNzEzW} 
```

### New Learnings
I can store the output of a command by setting it as a value to a variable.


## Reading input

In this challenge, your job is to use read to set the PWN variable to the value COLLEGE.
Good luck!

### Solve
**Flag:** pwn.college{8qaoG_XwbouK4CPK1z7pXbiwNa9.QX4cTN0wiM5AzNzEzW} 

used read to read the initial input and -p to get input as read -p "INPUT: " PWN.

```bash
read -p "INPUT: " PWN
INPUT: COLLEGE
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{8qaoG_XwbouK4CPK1z7pXbiwNa9.QX4cTN0wiM5AzNzEzW} 
```

### New Learnings
read command reads the data from my standard input and -p argument is used to get input into a variable.


## Reading files

Read /challenge/read_me into the PWN environment variable, and we'll give you the flag! The /challenge/read_me will keep changing,
so you'll need to read it right into the PWN variable with one command!

### Solve
**Flag:** pwn.college{wxF5pkc3pkJ6Rk1VOhzR8rnWi9i.QXwIDO0wiM5AzNzEzW}

read the file /challenge/read_me using < as  read "PWN" < /challenge/read_me.

```bash
read "PWN" < /challenge/read_me
You've set the PWN variable properly! As promised, here is the flag:
pwn.college{wxF5pkc3pkJ6Rk1VOhzR8rnWi9i.QXwIDO0wiM5AzNzEzW}
```

### New Learnings
read from the file using < .
