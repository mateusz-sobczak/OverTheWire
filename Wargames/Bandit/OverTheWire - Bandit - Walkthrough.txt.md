## Over The Wire Walkthrough - Bandit

### Table of Contents 
- [Bandit 0](#Bandit-0)
- [Bandit 1](#Bandit-1)
- [Bandit 2](#Bandit-2)
- [Bandit 3](#Bandit-3)
- [Bandit 4](#Bandit-4)
- [Bandit 5](#Bandit-5)
- [Bandit 6](#Bandit-6)
- [Bandit 7](#Bandit-7)
- [Bandit 8](#Bandit-8)
- [Bandit 9](#Bandit-9)
- [Bandit 10](#Bandit-10)
- [Bandit 11](#Bandit-11)
- [Bandit 12](#Bandit-12)
- [Bandit 13](#Bandit-13)
- [Bandit 14](#Bandit-14)
- [Bandit 15](#Bandit-15)
- [Bandit 16](#Bandit-16)
- [Bandit 17](#Bandit-17)
- [Bandit 18](#Bandit-18)
- [Bandit 19](#Bandit-19)
- [Bandit 20](#Bandit-20)
- [Bandit 21](#Bandit-21)
- [Bandit 22](#Bandit-22)
- [Bandit 23](#Bandit-23)
- [Bandit 24](#Bandit-24)
- [Bandit 25](#Bandit-25)
- [Bandit 26](#Bandit-26)
- [Bandit 27](#Bandit-27)
- [Bandit 28](#Bandit-28)
- [Bandit 29](#Bandit-29)
- [Bandit 30](#Bandit-30)
- [Bandit 31](#Bandit-31)
- [Bandit 32](#Bandit-32)
- [Bandit 33](#Bandit-33)

### Bandit 0

Official Tips: [Bandit0](https://overthewire.org/wargames/bandit/bandit0.html)

In bandit 0 all we need to do is login to the machine, both in Windows and Linux this is easily done with accessing the command line and executing the below command. 
```
ssh bandit0@bandit.labs.overthewire.org -p 2220
Password: bandit0
```

### Bandit 1
Official Tips: [Bandit1](https://overthewire.org/wargames/bandit/bandit1.html)

This level is pretty straightforward as one of the very 1st commands when logging into a new system is to perform the 'ls' command, as part of the enumeration of the file system. Once we run 'ls' command we can see a file named 'readme'. To see the file we can execute 'cat' command. There we can see the password to get to the next level.
```
ls
cat ./readme
```

To log out of the current ssh session, execute 'exit'. This will log you out and end the ssh session. Use the same ssh command to login to 'Bandit1' account as you used for 'Bandit0'. Remember to update the user. And copy over the password from the 'readme' file.

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

After logging in, perform the 'ls' command, you can see the file named '-'. The password is in that file...

This level is the same as level 1, the difficulty here is the hyphen name, if we would do 'cat -' the command line would assume it's a flag and it's part of the command rather then the file to display. To open the file you need to put in the exact path to the file.
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

This level is also the same as level 1 & 2, the only difference here is the file has spaces in the name. To open the file you can use a full path i.e.: './' and bash tab completion or type out the name, to open a file with spaces you need to escape the spaces using a '\'.

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

In this level we have 2 new concepts: directories and hidden files. As before, use the 'ls' command to see what files are available then use the 'cd' command to navigate to the available directory. To see the hidden file you will have to use the '-a' flag with the 'ls' command. In Linux hidden files are displayed with a full stop at the beginning of the name.

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

As always start the execise with 'ls' & navigate to the directory and execute the 'ls' command again. You will notice 10 files. Reading the official tips for this exercise, it says the password is in the human readable file. We can either open and read each file or we can use a 'file' command to determine the type of file. We will use '*' to check each file in one go.

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

Do the routine... Once you enter the 'inhere' directory and execute the 'ls' command you will see there are tons of files. If you run 'ls -l' you can see that all of them are directories. The password is probably hiding somewhere in one of them.

Using another useful flag with 'ls' command, we can list all of the files in each of the directories in one go 'ls -laR'. This gives us tons of files. None that we can straight away see as having the password in them. Looking at the official tips we can see the file we are looking for is of size 1033 bytes.

We can use this to our advantage with the grep command. 1st we need to execute the 'ls -laR' command the pipe the output to grep command to filter out what we are looking for. 'ls -laR | grep 1033' this will give us just one file '.file2'.

Assuming this is the right file we need to find out now which directory it is located in. Unfortunately we cannot see that from the output we are given, we can go back to the 'ls -laR' output and look through each '.file2' for the 1033 size and then see which directory it was in. Or we can edit our grep filter to include the directories too. 'ls -laR | grep -i -e .file2 -e maybehere -e 1033'. For handiness also include the right size.

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

The 1st step to this one is to take a look at the official tips. It says the file is located somewhere on the server. The best and easiest way is to use the 'find' command. Other tips say the file is owned by bandit7 and group bandit6, and size 33 bytes.

Using the flags '-user', '-group' and '-size' we can narrow down the files but unfortunately we get a lot of "Permission denied" errors, we can use '2>/dev/null' to redirect the stderr to the void, which should give us just one file.
```
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
cat /var/lib/dpkg/info/bandit7.password
```

Now use the password to login to Bandit 7.

```
exit
ssh bandit7@bandit.labs.overthewire.org -p 2220
Password: morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj 
```

References:
[find](https://man7.org/linux/man-pages/man1/find.1.html)
[stderr](https://askubuntu.com/questions/350208/what-does-2-dev-null-mean)

### Bandit 8
Official Tips: [Bandit8](https://overthewire.org/wargames/bandit/bandit8.html)

This level is quite simple as all we have to do it find the line with 'millionth' in the data.txt file.

```
grep millionth data.txt
```

Now use the password to login to Bandit 8.

```
exit
ssh bandit8@bandit.labs.overthewire.org -p 2220
Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```

### Bandit 9
Official Tips: [Bandit9](https://overthewire.org/wargames/bandit/bandit9.html)

This one is the same as bandit 8, the only difference we need to find a line that occurs only once. To do this we will need to use 'cat' instead of 'grep', so we could pipe the output to a 'uniq' command, which will identify the unique entries in the file. For unique to work we first need to 'sort' the output of cat before it becomes an input for 'uniq' command.

```
cat ./data.txt | sort | uniq -u
```

Now use the password to login to Bandit 9.

```
exit
ssh bandit9@bandit.labs.overthewire.org -p 2220
Password: 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
```

References:
[sort](https://man7.org/linux/man-pages/man1/sort.1.html)
[uniq](https://man7.org/linux/man-pages/man1/uniq.1.html)

### Bandit 10
Official Tips: [Bandit10](https://overthewire.org/wargames/bandit/bandit10.html)

Looking at the official tips it looks like all we need to do is to find human readable text inside of the 'data.txt' file. Using 'cat' and 'file' commands on the file shows us that this is a binary looking file. There are few ways we can solve this level, the easiest is by using 'strings' command. The tip also says there are a few '=' characters before the password.

```
strings ./data.txt | grep ===
```

Other way would be to use the 'cat' command and again use grep to find the line with '===' in it. This is a bit more tricky as grep would trow and error as the output of cat is not a text, looking at the man page we can see we can use '-a' flag to treat the input as text. This output is not as clean as the strings way but still works.

```
cat ./data.txt | grep -a ===
```

Now use the password to login to Bandit 10.

```
exit
ssh bandit10@bandit.labs.overthewire.org -p 2220
Password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey 
```

References:
[strings](https://man7.org/linux/man-pages/man1/strings.1.html)

### Bandit 11
Official Tips: [Bandit11](https://overthewire.org/wargames/bandit/bandit11.html)

The tip says the password is base64 encoded... Doing 'cat' on the file shows that it in fact is base64 encoded so all we need to do is decode it.

```
cat ./data.txt | base64 -d
```

Now use the password to login to Bandit 11.

```
exit
ssh bandit11@bandit.labs.overthewire.org -p 2220
Password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```

References:
[base64](https://man7.org/linux/man-pages/man1/base64.1.html)

### Bandit 12
Official Tips: [Bandit12](https://overthewire.org/wargames/bandit/bandit12.html)

[Explain]

```
```

Now use the password to login to Bandit 12.

```
exit
ssh bandit12@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 13
Official Tips: [Bandit13](https://overthewire.org/wargames/bandit/bandit13.html)

[Explain]

```
```

Now use the password to login to Bandit 13.

```
exit
ssh bandit13@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 14
Official Tips: [Bandit14](https://overthewire.org/wargames/bandit/bandit14.html)

[Explain]

```
```

Now use the password to login to Bandit 14.

```
exit
ssh bandit14@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 15
Official Tips: [Bandit15](https://overthewire.org/wargames/bandit/bandit15.html)

[Explain]

```
```

Now use the password to login to Bandit 15.

```
exit
ssh bandit15@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 16
Official Tips: [Bandit16](https://overthewire.org/wargames/bandit/bandit16.html)

[Explain]

```
```

Now use the password to login to Bandit 16.

```
exit
ssh bandit16@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 17
[id]: "17"
Official Tips: [Bandit17]](https://overthewire.org/wargames/bandit/bandit17.html)

[Explain]

```
```

Now use the password to login to Bandit [id].

```
exit
ssh bandit13@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)
