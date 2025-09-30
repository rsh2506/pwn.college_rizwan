# Practicing Piping

## Redirecting Output

redirect the output to a file which can be run to show the required output

### Solve
**Flag:** pwn.college{Y8O4SVsHCl5fIs8dcQ0qDiXhz9g.QX0YTN0wiM5AzNzEzW} 
 

```bash
 echo PWN > COLLEGE
 Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your flag:
 pwn.college{Y8O4SVsHCl5fIs8dcQ0qDiXhz9g.QX0YTN0wiM5AzNzEzW} 
```

### New Learnings
`>` command to redirect output


## Redirecting more output

we can redirect outputs for any command to a specific file

### Solve
**Flag:** pwn.college{os-PuLa-f0KiuNPLBHHfIervmAc.QX1YTN0wiM5AzNzEzW}  

redirecting the output for /challenge/run to myflag

```bash
/challenge/run > myflag  
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag
[HYPE] ONWARDS TO GREATNESS!
[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.
[TEST] You should have redirected my stdout to a file called myflag. Checking...
[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
cat myflag   
[FLAG] Here is your flag: 
[FLAG] pwn.college{os-PuLa-f0KiuNPLBHHfIervmAc.QX1YTN0wiM5AzNzEzW}
```

### New Learnings
redirecting outputs for any command 


## Appending output

adds on to previously saved data instead of overwriting it

### Solve
**Flag:** pwn.college{AKMXga8GfLzry0ie1MqhfgDcoSe.QX3ATO0wiM5AzNzEzW}  

append redirect the output for /challenge/run into /home/hacker/the-flag

```bash
/challenge/run 
/challenge/run >> /home/hacker/the-flag 
cat /home/hacker/the-flag  
 |
 \|/ This is the first half:
 v
 pwn.college{AKMXga8GfLzry0ie1MqhfgDcoSe.QX3ATO0wiM5AzNzEzW}^ that is the second half /|\|  
```

### New Learnings
i can now append outputs


## Redirecting errors

learning FD (file descriptor) numbers and how to redirect them 

### Solve
**Flag:** pwn.college{cm2kAq5Ee8v6om43Q6mT8Z1MQdp.QX3YTN0wiM5AzNzEzW}    


```bash
/challenge/run > myflag 2> instructions
cat instructions
cat myflag
[FLAG] Here is your flag:
[FLAG] pwn.college{cm2kAq5Ee8v6om43Q6mT8Z1MQdp.QX3YTN0wiM5AzNzEzW}
```

### New Learnings
redirecting standard errors


## Redirecting input

redirecting input to programs using <.

### Solve
**Flag:** > pwn.college{ceuHatt8iR0a58EJmN8qK98J96S.QXwcTN0wiM5AzNzEzW}

redirecting input for /challenge/run from PWN file containing the value COLLEGE.

```bash
echo COLLEGE > PWN
/challenge/run < PWN  
Reading from standard input... 
Correct! You have redirected the PWN file into my standard input, and I read the value 'COLLEGE' out of it! 
Here is your flag:
pwn.college{ceuHatt8iR0a58EJmN8qK98J96S.QXwcTN0wiM5AzNzEzW}  
```

### New Learnings
i can now redirect inputs to commands as well


## Grepping stored results

in this challenge we will practice redirecting output and grepping

### Solve
**Flag:** > pwn.college{sytL77UGx3xyV_xt665-pgkdJp3.QX4EDO0wiM5AzNzEzW} 

redirecting output of /challenge/run into /tmp/data.txt then grepping for the flag in that file

```bash
/challenge/run > /tmp/data.txt
grep pwn.college /tmp/data.txt 
pwn.college{sytL77UGx3xyV_xt665-pgkdJp3.QX4EDO0wiM5AzNzEzW}
```

### New Learnings
mastering to redirect outputs and grepping files


## Grepping live output

in this challenge, we will learn pipe operator to grap live output 

### Solve
**Flag:** > pwn.college{EJdaeS2j9cg005vgQjfRvvEOPho.QX5EDO0wiM5AzNzEzW}

```bash
challenge/run | grep pwn.college
[PASS] Success! You have satisfied all execution requirements. 
pwn.college{EJdaeS2j9cg005vgQjfRvvEOPho.QX5EDO0wiM5AzNzEzW}
```

### New Learnings
we learnt the pipe operator for grepping live output


## Grepping errors

using >& operator to redirect file descriptors.

### Solve
**Flag:** > pwn.college{8W27flhzcpj8DdnpWjuAs_qZBK2.QX1ATO0wiM5AzNzEzW} 

```bash
/challenge/run 2>& 1 | grep pwn.collegedelete_met
[PASS] Success! You have satisfied all execution requirements.
pwn.college{8W27flhzcpj8DdnpWjuAs_qZBK2.QX1ATO0wiM5AzNzEzW}
```

### New Learnings
i can now redirect standard error to standard output and then pipe them as normal.


## Filtering with grep -v
here we will learn to invert match (or look for lines which DO NOT include the search term)

### Solve
**Flag:** pwn.college{gl-R7sopv1roM3wCXJbk5D84Dev.0FOxEzNxwiM5AzNzEzW}

using grep with -v argument

```bash
/challenge/run | grep -v DECOY
pwn.college{gl-R7sopv1roM3wCXJbk5D84Dev.0FOxEzNxwiM5AzNzEzW}
```

### New Learnings
i can now invert match.


## Duplicating piped data with tee

we will learn about the tee command, named after a "T-splitter" from plumbing pipes, duplicates data flowing through your pipes to any number of files provided on the command .

### Solve
**Flag:**

moved /flag to /tmp/hack-the-planet then run /challenge/check to get the flag.

```bash

```

### New Learnings


## Process substitution for input

Here, you'll diff two sets of command outputs: /challenge/print_decoys, which will print a bunch of decoy flags, and /challenge/print_decoys_and_flag which will print those same decoys plus the real flag.
Use process substitution with diff to compare the outputs of these two programs and find your flag!

### Solve
**Flag:** pwn.college{Id1jesX71slzCWt1LPZT8FrFVF6.0lNwMDOxwiM5AzNzEzW} 

comparing the outputs of decoy programs to find the real flag. we're using input process substitution.

```bash
diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
30a31
> pwn.college{Id1jesX71slzCWt1LPZT8FrFVF6.0lNwMDOxwiM5AzNzEzW} 
```

### New Learnings
diff command

## Writing to multiple programs
process substitution for duplicating to 2 commands

### Solve
**Flag:** pwn.college{I69sWb8XMpfripn2vDOyOVq-YM_.QXwgDN1wiM5AzNzEzW}


```bash
/challenge/hack | tee >(/challenge/the) | /challenge/planet
Congratulations, you have duplicated data into the input of two programs!
Here is your flag: pwn.college{I69sWb8XMpfripn2vDOyOVq-YM_.QXwgDN1wiM5AzNzEzW} 
```

### New Learnings
using process substitution to write for multiple programs


## Split-piping stderr and stdout

### Solve
**Flag:** pwn.college{cyZnCgdl3fsepqAk8FoZBhq52kd.QXxQDM2wiM5AzNzEzW}


```bash
/challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that
even experts struggle with! Here is your flag:
pwn.college{cyZnCgdl3fsepqAk8FoZBhq52kd.QXxQDM2wiM5AzNzEzW}
```

### New Learnings
intensive use of piping

## Named pipes
introduction to FIFOs

### Solve
**Flag:** 

```bash

```
### New Learnings



















