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
exit
ssh bandit1@bandit.labs.overthewire.org -p 2220
Password: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

References:
[ls](https://man7.org/linux/man-pages/man1/ls.1.html)
[cat](https://man7.org/linux/man-pages/man1/cat.1.html)

### Bandit 2
Official Tips: [Bandit1](https://overthewire.org/wargames/bandit/bandit2.html)

After logging in perform the 'ls' command, you can see file name '-'. The password is in that file...

This level is same as level 1, the difficulty here is the hyphen name, if we would do 'cat -' the command line would assume it's a flag and it's part of the command rather then the file to display. To open the file you need to put in the exact path to the file.
```
ls
cat ./-
```

Now use the password to login to Bandit 3.

```
exit
ssh bandit1@bandit.labs.overthewire.org -p 2220
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

### Bandit 3
Official Tips: [Bandit3](https://overthewire.org/wargames/bandit/bandit3.html)

This level is also the same as level 1 & 2 only difference here is the file has spaces in the name. To open the file you can use bash tab completion or type out the name, to open a file with spaces you need to escape the spaces using a '\'.

```
ls
cat ./--spaces\ in\ this\ filename--
```

```
exit
ssh bandit1@bandit.labs.overthewire.org -p 2220
Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```


### Bandit 4
Official Tips: [Bandit4](https://overthewire.org/wargames/bandit/bandit4.html)



```
```
