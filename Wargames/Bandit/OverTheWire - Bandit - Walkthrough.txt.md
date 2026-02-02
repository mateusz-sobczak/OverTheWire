## Over The Wire Walkthrough - Bandit

### Bandit 0

Official Tips: [Bandit0](https://overthewire.org/wargames/bandit/bandit0.html)

In bandit 0 all we need to do in login to the machine, both in Windows and Linux this is easily done with accessing the command line and executing the below command. 
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
Password: bandit0
```

### Bandit 1
Official Tips: [Bandit1](https://overthewire.org/wargames/bandit/bandit1.html)

This level is pretty straight forward as one of the very 1st commands when login into a new system is to perform the 'ls' command, as part of the enumeration of the file system. Once we run 'ls' command we can see a file names 'readme'. To see the fine we can execute 'cat' command. There we can see the password to get to the next level.
```
ls
cat ./readme
```

To log out of the current ssh session execute 'exit'. This will log you out and end the ssh session. Use the same ssh command to login to 'Bandit1' account as for 'Bandit0'. Remember to update the user. And copy over the password from the 'readme' file.

```
ssh bandit1@bandit.labs.overthewire.org -p 2220
Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

References:
[ls](https://man7.org/linux/man-pages/man1/ls.1.html)
[cat](https://man7.org/linux/man-pages/man1/cat.1.html)

### Bandit 2
Official Tips: [Bandit2](https://overthewire.org/wargames/bandit/bandit2.html)

After logging in 
```
```
### Bandit 3
Official Tips: [Bandit3](https://overthewire.org/wargames/bandit/bandit3.html)
```
```
