# Data Manipulation

## Translating characters

Now, you try it! In this level, /challenge/run will print the flag
but will swap the casing of all characters (e.g., A will become a and vice-versa).
Can you undo it with tr and get the flag?

### Solve
**Flag:** pwn.college{8enhuC7mXx9NZ97LAG44E24YoU0.01MxEzNxwCN3AzNzEzW}
swapped all the uppercase characters A-Z to lower case a-z as tr 'a-z A-Z' 'A-Z a-z' .
 

```bash
/challenge/run
Your case-swapped flag:
PWN.COLLEGE{8ENHUc7MxX9nz97lag44e24yOu0.01mXeZnXWcn3aZnZeZw}
echo PWN.COLLEGE{8ENHUc7MxX9nz97lag44e24yOu0.01mXeZnXWcn3aZnZeZw} | tr 'a-z A-Z' 'A-Z a-z'
pwn.college{8enhuC7mXx9NZ97LAG44E24YoU0.01MxEzNxwCN3AzNzEzW}
```

### New Learnings
case swap using tr command

## Deleting characters

 Now you give it a try. I'll intersperse some decoy characters (specifically: ^ and %)
 among the flag characters. Use tr -d to remove them!

### Solve
**Flag:** pwn.college{sf-qDBK0p3pFoXjHNn2JD2l7_i9.0FNxEzNxwCN3AzNzEzW}
deleted the unnecessary characters in string using tr -d as tr -d %^  

```bash
/challenge/run
Your character-stuffed flag:
p%w^%n%.^c%o^%lle^g^e%{^%s%f-^q^%D^%BK0^%p%3%p^F^%o^Xj^%H^%N^%n%2^J^D^2%l%7%_^%i%9%.%0F%N^x^%Ez^N^%x^%w^%C%N%3%A%zN%z%E^z^W^}^%%
 echo p%w^%n%.^c%o^%lle^g^e%{^%s%f-^q^%D^%BK0^%p%3%p^F^%o^Xj^%H^%N^%n%2^J^D^2%l%7%_^%i%9%.%0F%N^x^%Ez^N^%x^%w^%C%N%3%A%zN%z%E^z^W^}^%% | tr -d %^
pwn.college{sf-qDBK0p3pFoXjHNn2JD2l7_i9.0FNxEzNxwCN3AzNzEzW}
```

### New Learnings
can delete characters like '!@#$%^&' using tr -d command.


## Deleting newlines

Now, let's combine this with deletion. In this challenge, we'll inject a bunch of newlines into the flag. Delete them with tr's -d flag and the escaped newline specification!

### Solve
**Flag:** pwn.college{8IyLPcKT7p7vSTlsa38mhqURApi.0VNxEzNxwCN3AzNzEzW}

swapped all the uppercase characters A-Z to lower case a-z as tr 'a-z A-Z' 'A-Z a-z' .
 

```bash
/challenge/run
Your line-split flag:
p
w
n.
co
lleg
e
{
8I
y
LPcK
T7
p
7
v
S
T
l
sa3
8
m
hqURA
p
i.
0
V
Nx
Ez
N
x
wC
N
3A
zN
z
EzW}
 echo "Your line-split flag:
p
w
n.
co
lleg
e
{
8I
y
LPcK
T7
p
7
v
S
EzW}" | tr -d "\n"
Your line-split flag:pwn.college{8IyLPcKT7p7vSTlsa38mhqURApi.0VNxEzNxwCN3AzNzEzW}
```

### New Learnings
can delete newline character using tr -d command.


## Extracting the first lines with head 

This challenge's /challenge/pwn outputs a bunch of data, and you'll need to pipe it through head to grab just the first 7 lines and then pipe them onwards to /challenge/college, which will give you the flag if you do this right! Your solution will be a long composite command with two pipes connecting three commands.

### Solve
**Flag:** pwn.college{0R8IPC55t5uRU54T0Owat53S-ef.0lNxEzNxwCN3AzNzEzW}

Grab first 7 lines from /challenge/pwn using head then pipe it to /challenge/college as 
/challenge/pwn | head -n 7 | /challenge/college

```bash
/challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{0R8IPC55t5uRU54T0Owat53S-ef.0lNxEzNxwCN3AzNzEzW}
```

### New Learnings
can grab data from one file using head can grab any no. of lines using head -n option and then pipe it to another file.


## Extracting specific sections of text 

In this challenge, the /challenge/run program will give you a bunch of lines with random numbers and single characters (characters of the flag) as columns. Use cut to extract the flag characters, then pipe them to tr -d "\n" (like the previous level!) to join them together into a single line. Your solution will look something like /challenge/run | cut ??? | tr ???, with the ??? filled out.

### Solve
**Flag:** pwn.college{0-vPurQm1Sk21W1L07FGY11_Xdf.01NxEzNxwCN3AzNzEzW}

grab 2nd column from /challenge/run then remove the newline character as /challenge/run | cut -d " " -f 2 | tr -d "\n"

```bash
/challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{0-vPurQm1Sk21W1L07FGY11_Xdf.01NxEzNxwCN3AzNzEzW}
```

### New Learnings
can  extract specific part of line using cut command


## Sorting data

In this challenge, there's a file at /challenge/flags.txt containing 100 fake flags, with the real flag mixed among them. When sorted alphabetically, the real flag will be at the end (we made sure of this when generating fake flags). Go get it!

### Solve
**Flag:** pwn.college{cjcOdLZXCnGGEiX3k-oWxYF62VO.0FM0MDOxwCN3AzNzEzW}

sorting the flags as sort /challenge/flags.txt -r the flags are sorted in reverse to first one will be real flag. 

```bash
sort /challenge/flags.txt -r
pwn.college{cjcOdLZXCnGGEiX3k-oWxYF62VO.0FM0MDOxwCN3AzNzEzW}
.
.
.
.
ovm.cnlldge{bjcOdLZXCmGGDiW3k-nWxYE62VO.0EM0MDOxwCN3AzNzEzW}
```

### New Learnings
can sort lines using sort command.
