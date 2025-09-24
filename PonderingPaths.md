# Pondering Paths

## The root 
invoke a program by providing its path on the command line.

### Solve
**Flag:** pwn.college{MdR0x7yzoQ1I4a6Y5i8UjJZONXF.QX4cTO0wiM5AzNzEzW}

written /pwn  

```bash
/pwn
BOOM!!!
Here is your flag:
pwn.college{MdR0x7yzoQ1I4a6Y5i8UjJZONXF.QX4cTO0wiM5AzNzEzW}
```

### New Learnings
absolute path.


## Program and absolute paths 

execute the run file that is in the challenge directory that is, in turn, in the / directory.

### Solve
**Flag:** pwn.college{su50mOGzteC2FWwCqlQufo1_xzi.QX1QTN0wiM5AzNzEzW}

accessed the run file in the challenge directory which is in / directory.

```bash
/challenge/run

Correct!!!

/challenge/run is an absolute path! Here is your flag:

pwn.college{su50mOGzteC2FWwCqlQufo1_xzi.QX1QTN0wiM5AzNzEzW}
```

### New Learnings
file inside a directory.


## Position thy self

execute the /challenge/run program from a specific path '/'.

### Solve
**Flag:** pwn.college{odcdvzDcdz1U-sLXl2QAckFVS3B.QX2QTN0wiM5AzNzEzW} 

first change the directory from ~ to / then accessed the run file in challenge directory. 

```bash
cd /usr/share/doc
/challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{odcdvzDcdz1U-sLXl2QAckFVS3B.QX2QTN0wiM5AzNzEzW} 
```

### New Learnings
'~' shows the current path and 'cd' to change the directory to '/'.


## Position elsewhere

execute the /challenge/run program from a specific path '/home'

### Solve
**Flag:** pwn.college{wvbtUPd4QWkSl-On_qi4ALLpNdD.QX3QTN0wiM5AzNzEzW}

first change the directory from ~ to /home then accessed the run file in challenge directory. 

```bash
cd /
/challenge/run
Incorrect...
You are not currently in the /usr/share/doc directory.                                                 
Please use the `cd` utility to change directory appropriately.
cd /home
/challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{wvbtUPd4QWkSl-On_qi4ALLpNdD.QX3QTN0wiM5AzNzEzW}
```

### New Learnings
access a file from different directory '/home'.


## Position yet elsewhere

execute the /challenge/run program from a specific directory '/tmp'

### Solve
**Flag:** pwn.college{EbrVIOr2FcFboAcWtIcG-wWEvRa.QX4QTN0wiM5AzNzEzW}

first change the directory from ~ to /tmp then /challenge/run.

```bash
cd /
/challenge/run
Incorrect...
You are not currently in the /proc/131/fd directory.                                                    
Please use the `cd` utility to change directory appropriately. 
cd /tmp
/challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{EbrVIOr2FcFboAcWtIcG-wWEvRa.QX4QTN0wiM5AzNzEzW}
```

### New Learnings
access a file from different path '/tmp'.


## implicit relative paths , from '/'

run /challenge/run using a relative path while having a current working directory of '/' .

### Solve
**Flag:** pwn.college{Qs2MHrhdLgWZ3vJDd2gFdOKXaZ2.QX5QTN0wiM5AzNzEzW}   

first change the directory from ~ to / then challenge/run .

```bash
cd /
challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Qs2MHrhdLgWZ3vJDd2gFdOKXaZ2.QX5QTN0wiM5AzNzEzW}   
```

### New Learnings
access a file by using relative path.


## explicit relative paths , from '/'

run /challenge/run explicitly using a '.' in my relative path while having a current working directory of '/' 

### Solve
**Flag:** pwn.college{wz7_nw21mwy6O3EeTIdLJmquOSF.QXwUTN0wiM5AzNzEzW}
first change the directory from ~ to / then ./challenge/run

```bash
cd /
./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{wz7_nw21mwy6O3EeTIdLJmquOSF.QXwUTN0wiM5AzNzEzW}
```

### New Learnings
access a file explicitly by using '.' in relative path.


## implicit relative paths 

This challenge will need you to run it from the /challenge directory . Explicitly use relative paths to launch 'run'.

### Solve
**Flag:** pwn.college{YhxgUsCTtjnSFf8MPS9qjKztrXg.QXxUTN0wiM5AzNzEzW}
first change the directory from ~ to /challenge then ./run

```bash
cd /challenge
./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{YhxgUsCTtjnSFf8MPS9qjKztrXg.QXxUTN0wiM5AzNzEzW}
```

### New Learnings
access a file explicitly by using '.' in relative path. from /challenge directory.


## home sweet home 

In this challenge, /challenge/run will write a copy of the flag to any file you specify as an argument on the commandline.

### Solve
**Flag:** pwn.college{wrhBvvZgU9SvW3RZAzc_G8jmezu.QXzMDO0wiM5AzNzEzW}

copying flag from /challenge/run and writting on specific file

```bash
/challenge/run ~/~
Writing the file to /home/hacker/~!
... and reading it back to you:
pwn.college{wrhBvvZgU9SvW3RZAzc_G8jmezu.QXzMDO0wiM5AzNzEzW}
```

### New Learnings
copying flag to any specific file as an argument on the commandline.



