# Processes and Jobs

## Listing Processes

In this level, I have once again renamed /challenge/run to a random filename, and this time made it so that you cannot ls the /challenge directory! But I also launched it, so you can find it in the running process list, figure out the filename, and relaunch it directly for the flag! 

### Solve
**Flag:** pwn.college{YDNw9whO6eHqKc1FO0iMN4kHJbN.QX4MDO0wCN3AzNzEzW}

got all the files running using ps command with argument -ef as ps -ef then read the running /challenge/run file which was renamed as /challenge/9689-run-1632.

```bash
ps -ef
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 07:26 ?        00:00:00 /sbin/docker-init -- /nix/var/nix/
root           7       1  0 07:26 ?        00:00:00 /run/dojo/bin/sleep 6h
root         132       1  0 07:26 ?        00:00:00 /challenge/9689-run-1632
root         135     132  0 07:26 ?        00:00:00 sleep 6h
hacker       137       0  0 07:26 pts/0    00:00:00 /nix/store/0nxvi9r5ymdlr2p24rjj9qz
hacker       143     137  0 07:26 pts/0    00:00:00 /run/dojo/bin/bash --login
hacker       154     143  0 07:26 pts/0    00:00:00 ps -ef
/challenge/9689-run-1632
Yahaha, you found me! Here is your flag:
pwn.college{YDNw9whO6eHqKc1FO0iMN4kHJbN.QX4MDO0wCN3AzNzEzW}
Now I will sleep for a while (so that you could find me with 'ps').

```

### New Learnings
ps command and arguments -ef and aux.


## Killing Processes

In this challenge, /challenge/run will refuse to run while /challenge/dont_run is running! You must find the dont_run process and kill it. If you fail, pwn.college will disavow all knowledge of your mission. 

### Solve
**Flag:**  pwn.college{gKglgwM6Ym5UIeLjXWgr-MnJgvn.QXyQDO0wCN3AzNzEzW}

used ps command with argument aux to see the PID of /challenge/dont_run then used kill command to close the process as kill /challenge/dont_run. 

```bash
ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   1056   640 ?        Ss   07:35   0:00 /sbin/docker-init -
root           7  0.0  0.0 231708  2560 ?        S    07:35   0:00 /run/dojo/bin/sleep
root         135  0.0  0.0   5204  3520 ?        S    07:35   0:00 su -c /challenge/.l
hacker       136  0.0  0.0 231576  3520 ?        Ss   07:35   0:00 /challenge/dont_run
hacker       137  0.0  0.0 231708  2560 ?        S    07:35   0:00 sleep 6h
hacker       139  0.0  0.0 231576  3520 pts/0    Ss   07:35   0:00 /nix/store/0nxvi9r5
hacker       145  0.0  0.0 231940  4160 pts/0    S+   07:35   0:00 /run/dojo/bin/bash
hacker       167  0.0  0.0 231576  3520 pts/1    Ss   07:37   0:00 /nix/store/0nxvi9r5
hacker       173  0.0  0.0 231940  4160 pts/1    S    07:37   0:00 /run/dojo/bin/bash
hacker       190  0.0  0.0 233600  3840 pts/1    R+   07:39   0:00 ps aux
kill 136
/challenge/run
Great job! Here is your payment:
pwn.college{gKglgwM6Ym5UIeLjXWgr-MnJgvn.QXyQDO0wCN3AzNzEzW}
```

### New Learnings
kill command can close a running process.


## Interrupting Processes

In this challenge, /challenge/run will refuse to give you the flag until you interrupt it.  

### Solve
**Flag:**  pwn.college{cSeeIRpoUtvbIxd8MoZwK_dk2Is.QXzQDO0wCN3AzNzEzW}

run /challenge/run then pressed c while holding ctrl.

```bash
/challenge/run
I could give you the flag... but I won't, until this process exits. Remember,
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{cSeeIRpoUtvbIxd8MoZwK_dk2Is.QXzQDO0wCN3AzNzEzW}
```

### New Learnings
ctrl-C interrupts the process running.it causes the application to cleanly exit.


## Killing misbehaving processes

In this challenge, there's a decoy process that's hogging a critical resource - a named pipe (FIFO) at /tmp/flag_fifo into which (like in the Practicing Piping FIFO challenge) /challenge/run wants to write your flag. You need to kill this process.

Your general workflow should be:

1. Check what processes are running.
2. Find /challenge/decoy in the list and figure out its process ID.
3. kill it.
4. Run /challenge/run to get the flag without being overwhelmed by decoys (you don't need to
   redirect its output; it'll write to the FIFO on its own).


### Solve
**Flag:**  


```bash

```

### New Learnings


## Suspending processes

This level's run wants to see another copy of itself running and using the same terminal. How? Use the terminal to launch it, then suspend it, then launch another copy while the first is suspended!

### Solve
**Flag:**  pwn.college{cPRed4iKKftBuKhDj7yI0p6smZg.QX1QDO0wCN3AzNzEzW}

running /challenge/run then suspending it using ctrl-Z then running a copy of the same process.

```bash
/challenge/run

I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can
background me with Ctrl-Z or, if you're not ready to do that for whatever
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run

/challenge/run

I'll only give you the flag if there's already another copy of me running in
this terminal... Let's check!

Yay, I found another version of me! Here is the flag:
pwn.college{cPRed4iKKftBuKhDj7yI0p6smZg.QX1QDO0wCN3AzNzEzW}
```

### New Learnings
ctrl-Z can suspend a process to the backround.


## Resuming processes

This challenge's run needs you to suspend it, then resume it. Good luck!

### Solve
**Flag:**  pwn.college{YN3aeMbvsQwssp9jCg6vK-SNrdr.QX2QDO0wCN3AzNzEzW}

suspending the process by pressing ctrl-Z and then resuming it using fg command.

```bash
/challenge/run

Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run

fg
/challenge/run
I'm back! Here's your flag:
pwn.college{YN3aeMbvsQwssp9jCg6vK-SNrdr.QX2QDO0wCN3AzNzEzW}
Don't forget to press Enter to quit me!

Goodbye!
```

### New Learnings
fg command can resume a suspended process.


## Backgrounding processes

This challenge's run needs you to suspend it, then resume it. Good luck!

### Solve
**Flag:**  pwn.college{oDvVAQZoilUJPn6hcpiZ4KJ18Hl.QX3QDO0wCN3AzNzEzW}

run /challenge/run then sespended it using ctrl-Zand backgrounded it using bg commang launched another copy of /challenge/run.

```bash
/challenge/run

I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!
[1]+  Stopped                 /challenge/run
^Z
[1]+  Stopped                 /challenge/run

/challenge/run

I'll only give you the flag if there's already another copy of me running *and
not suspended* in this terminal... Let's check!

I found a second version of me, but it's suspended! Please resume it in the
background with the 'bg' command, then run me again.

bg
[1]+ /challenge/run &

Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out.

/challenge/run

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{oDvVAQZoilUJPn6hcpiZ4KJ18Hl.QX3QDO0wCN3AzNzEzW}
```

### New Learnings
backgrounding a process using bg command.


## Foregrounding processes

Well, you can foreground a backgrounded process with fg just like you foreground a suspended process! This level will walk you through that!

### Solve
**Flag:**  pwn.college{kDpEkYijOPtPqjXUVeKcAQMIlm7.QX4QDO0wCN3AzNzEzW}

suspended the program by ctrl-Z then backgrounded it by bg and then foregrounded it by fg.

```bash
/challenge/run
To pass this level, you need to suspend me, resume the suspended process in the
background, and *then* foreground it without re-suspending it! You can
background me with Ctrl-Z (and resume me in the background with 'bg') or, if
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run

bg
[1]+ /challenge/run &

Yay, I'm now running the background! Because of that, this text will probably
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times
to scroll this text out. After that, resume me into the foreground with 'fg';
I'll wait.

fg
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{kDpEkYijOPtPqjXUVeKcAQMIlm7.QX4QDO0wCN3AzNzEzW}
```

### New Learnings
foregrounding a process using fg command.


## Starting backgrounded processes

Now it's your turn to practice! Launch /challenge/run backgrounded for the flag!

### Solve
**Flag:**  pwn.college{ohugNfxG786zNNNG4SyUB7RxEfE.QX5QDO0wCN3AzNzEzW}

running the /challenge/run in background using & argument as /challenge/run &.

```bash
/challenge/run &
[1] 141

Yay, you started me in the background! Because of that, this text will probably
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{ohugNfxG786zNNNG4SyUB7RxEfE.QX5QDO0wCN3AzNzEzW}

[1]+  Done                    /challenge/run
```

### New Learnings
can run a process in backround using & argument.


## Process exit codes

In this challenge, you must retrieve the exit code returned by /challenge/get-code and then run /challenge/submit-code with that error code as an argument. Good luck!

### Solve
**Flag:**  pwn.college{smI0_RLlLA_NMxUpAiT2t9OQp9R.QX5YDO1wCN3AzNzEzW}

run the /challenge/get-code and get the exit code by using ? variable and prepend it with $ as echo $? to read the exit code and then run the /challenge/submit-code with the exit code as /challenge/submit-code [EXIT_CODE] . 

```bash
/challenge/get-code
Exiting with an error code!

echo $?
1

/challenge/submit-code 1
CORRECT! Here is your flag:
pwn.college{smI0_RLlLA_NMxUpAiT2t9OQp9R.QX5YDO1wCN3AzNzEzW}
```

### New Learnings
? variable. can be used to read the exit code of a program. And to read its value we have to prepend it with $.
