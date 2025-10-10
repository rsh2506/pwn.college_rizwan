# Terminal Multiplexing

## Launching Screen

screen is a program that creates virtual terminals inside your terminal. It's somewhat like having multiple browser tabs, but for your command line.

### Solve
**Flag:** pwn.college{4r5jMnQbKXVM0G9wSPOjrI7juC5.0VN4IDOxwiM5AzNzEzW}
 

```bash
screen
pwn.college{4r5jMnQbKXVM0G9wSPOjrI7juC5.0VN4IDOxwiM5AzNzEzW}
```

### New Learnings
`screen` command to make virtual terminals

## Detaching and Attaching

in this challenge we will learn to detach and reattach our virtual terminal

### Solve
**Flag:** pwn.college{8O31ldBJ7YU55S1lPCJT9flSpVr.0lN4IDOxwiM5AzNzEzW}

```bash
screen
[Enter]
[CTRL+A, D]
/challenge/run
screen -r
echo Yes! Flag is: pwn.college{8O31ldBJ7YU55S1lPCJT9flSpVr.0lN4IDOxwiM5AzNzEzW}
```

### New learnings
i can now detach and reattach screen.


## Finding Sessions

in this challenge we will learn to detach/reattach to a particular screen if many screen sessions are running.

### Solve
**FLAG:** pwn.college{QeBP3WdHnE_vVWjoNTCrAB6tSMf.01N4IDOxwiM5AzNzEzW}

```bash
screen -ls
screen -r session_edcc89424878a5e1 
pwn.college{QeBP3WdHnE_vVWjoNTCrAB6tSMf.01N4IDOxwiM5AzNzEzW}
```

### New learnings
i can now navigate through multiple screen sessions.

## Switching Windows

in this challenge we will learn about switching through multiple windows in a single screen session.

### Solve

**Flag:** pwn.college{UCxmkSW5SRGJRKT5fMGU7JJ0QL-.0FO4IDOxwiM5AzNzEzW}

```bash
screen -r
[CTRL+A, 0]
Here is your flag: pwn.college{UCxmkSW5SRGJRKT5fMGU7JJ0QL-.0FO4IDOxwiM5AzNzEzW}
```
### New learnings
i can now easily nagivate through different windows for a single screen session.

## Detaching and Attaching (tmux)

tmux (terminal multiplexer) is screen's younger, more modern cousin. It does all the same things but with some different key bindings. The biggest difference? Instead of Ctrl-A, tmux uses Ctrl-B as its command prefix.

### Solve
**Flag:** pwn.college{4wEmIzLq89T0TV2vNQ_ypA_9Xji.0VO4IDOxwiM5AzNzEzW}

```bash
tmux
[CTRL+B, d]
/challenge/run
tmux a
Congratulations, here is your flag: pwn.college{4wEmIzLq89T0TV2vNQ_ypA_9Xji.0VO4IDOxwiM5AzNzEzW}
```

### New learnings
learning to detach/reattach in `tmux`

## Switching Windows (tmux)

Just like screen, tmux has windows. The key combos are different, but the concept is the same.

### Solve
**Flag:** 
















