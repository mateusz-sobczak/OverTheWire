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
ssh bandit2@bandit.labs.overthewire.org -p 2220
Password: 263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

### Bandit 3
Official Tips: [Bandit3](https://overthewire.org/wargames/bandit/bandit3.html)

This level is also the same as level 1 & 2 only difference here is the file has spaces in the name. To open the file you can use a full path i.e.: './' and bash tab completion or type out the name, to open a file with spaces you need to escape the spaces using a '\'.

```
ls
cat ./--spaces\ in\ this\ filename--
```

Now use the password to login to Bandit 3.

```
exit
ssh bandit3@bandit.labs.overthewire.org -p 2220
Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

### Bandit 4
Official Tips: [Bandit4](https://overthewire.org/wargames/bandit/bandit4.html)

In this level we have 2 new concepts directories and hidden files. As before use the 'ls' command to see what files are available than use the 'cd' command to navigate to the available directory. To see the hidden file you will have to use the '-a' flag with the 'ls' command. In Linux hidden files are displayed with a fullstops at the beginning of the name.

```
ls
cd inhere
ls -a
cat ./...Hiding-From-You
```

Now use the password to login to Bandit 4.

```
exit
ssh bandit4@bandit.labs.overthewire.org -p 2220
Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

References:
[cd](https://man7.org/linux/man-pages/man1/cd.1p.html)

### Bandit 5
Official Tips: [Bandit5](https://overthewire.org/wargames/bandit/bandit5.html)

As always start the execise with 'ls' & navigate to the directory and execute the 'ls' command again. You will notice 10 files. Readding the official tips for this exercise, it says the password is in the human readable file. We can either open and read each file or we can use a 'file' command to determind the type of the file. We will use '*' to check each file in one go.

```
ls
cd inhere
file ./-file0*
```

From the output we can see one file is of type ASCII text, this is probably the one... Use 'cat' to check

```
cat ./-file07
```

Now use the password to login to Bandit 5.

```
exit
ssh bandit5@bandit.labs.overthewire.org -p 2220
Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 6
Official Tips: [Bandit6](https://overthewire.org/wargames/bandit/bandit6.html)

Do the routine... Once you enter the 'inhere' directory and execute the 'ls' command you will see there are tones of files. If you run 'ls -l' you can see that all of them are directories. The password is probably hiding somewhere in one of them.

Using another useful flag with 'ls' command, we can list all of the files in each of the directories in one go 'ls -laR'. This gives us tones of files. None that we can straight away see as having the password in them. Looking at the official tips we can see the file we are looking for is of size 1033 bytes.

We can use this to our advantage with the grep command. 1st we need to execute the 'ls -laR' command the pipe the output to grep command to filter out what we are looking for. 'ls -laR | grep 1033' this will give us just one file '.file2'.

Assuming this is the right file we need to find now in which directory is it located in. Unfortunately we cannot see that from the output we are given, we can go back to the 'ls -laR' output and look through each '.file2' for the 1033 size and than see which directory was it in. Or we can edit our grep filter to include the directories too. 'ls -laR | grep -i -e .file2 -e maybehere -e 1033'. For handiness also include the right size.

```
ls 
cd inhere
ls -laR | grep -i -e maybehere -e .file2 -e 1033
```

This cleans up the output nicely for us. We only have 11 lines to look at and only one file and looking at the line above we can see the file is located in the 'maybehere07' directory. Now lets see the file and get the password.

```
cat ./maybehere07/.file2
```

Now use the password to login to Bandit 6.

```
exit
ssh bandit6@bandit.labs.overthewire.org -p 2220
Password: HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```

References:
[grep](https://man7.org/linux/man-pages/man1/grep.1.html)

### Bandit 7
Official Tips: [Bandit7](https://overthewire.org/wargames/bandit/bandit7.html)

[Explain]

```
```

Now use the password to login to Bandit 6.

```
exit
ssh bandit6@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 7
Official Tips: [Bandit7](https://overthewire.org/wargames/bandit/bandit7.html)

[Explain]

```
```

Now use the password to login to Bandit 6.

```
exit
ssh bandit6@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)
