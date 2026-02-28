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

The official tips say all the letters in 'data.txt' have been moved by 13 characters. Doing a 'cat' on the file, shows us it's in the same format as the decoded password for level 11: "The password is xxx". So we know the 'G' needs to be a 'T'. Outside of decoding the password manually the tips gives a tool named 'tr' checking out man pages, we can see the tool allows us to translate or swap characters for different ones, this level is interesting cause I didn't know of a 'tr' command before. 

The 'tr' command at the most basic level takes 2 arguments the character set the msg is in and a character set to translate it to, meaning if we would do 'tr [A-Z] [a-z]' this would make all the upper case characters to lowercase. We can also do shift patterns, 'tr [G] [T]' would translate all 'G' characters to 'T'. Now we need to build a character set.

We can use python one-liners to find the exact letters without having to manually count out what A+13 is `python3 -c "print(chr(ord('A') +13))"`. This tells us that 'A' becomes 'N', as letter before 'N' is 'M' so this would make '[A-M] [N]'. Now we need to find what 'M' would translate to. Using the exact same python script but replacing the 'A' with 'M' gives us 'Z'

Now we need to translate N-Z, we can assume as there are 26 characters in the alphabet and 13 is the halfway point, 'A'  &rarr; 'N' and 'M' &rarr; 'Z' it would be the reverse 'N' &rarr; 'A' and 'Z' &rarr; 'M'.

Meaning our basic 'tr' command would look like this 'tr [A-MN-Z] [N-ZA-M]'. Now we just need to replicate this for all the lower case characters.

```
cat data.txt | tr [A-MN-Z][a-mn-z] [N-ZA-M][n-za-m]
```

Now use the password to login to Bandit 12.

```
exit
ssh bandit12@bandit.labs.overthewire.org -p 2220
Password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```

References:
[tr](https://man7.org/linux/man-pages/man1/tr.1.html)
[Python CMD](https://docs.python.org/3/using/cmdline.html#cmdoption-c)

### Bandit 13
Official Tips: [Bandit13](https://overthewire.org/wargames/bandit/bandit13.html)

This is a fun but confusing exercise there are multiple layers to this puzzle, the tips tell us the file is a hexdump of a file compressed multiple times. They tell use to use a temporary working space too. Let's start by getting our working space setup. We can achieve this with a few useful commands and tricks to do in a nice and neat one-liner.

```
cd $(mktemp -d) && cp ~/data.txt .
```

This command while it might look confusing is straight forward, we can read it like a math problem from left to right and what's in the brackets get's done first. Firstly bash executes 'mktemp -d' command which will create us a temporary directory in the '/tmp/' folder, than it will change directory to the folder, it could be done individually but to save us time typing out the random name of the directory we can use the '$()' or put the command in backticks (both will achieve the same result), which will substitute the directory for us. Once we are in the directory we can copy over the working file from bandit12's home directory.

Now we can start looking at what we are working with. 

The tips told us the file is a hex dump. Executing the `cat data.txt` will show that it is in fact a hex file. Looking at the output of 'cat' we can see that the file starts with '1f8b 0808' doing a google search shows us this is a gzip'd file. Trying to uncompress it with 'gzip' will not work as currently this is just a text file we need to convert it back into a data file. We can do it with a 'xxd' command. Then we can uncompress it with 'gzip'.

```
xxd -r data.txt data.gz
gzip -d data.gz
```

What we end up with is the 'data' file. Now the tips told us this is a multi compressed file. So lets have a look what else we need to do. As this is now a data file the 'cat' command will not help us out a lot, but we can still use 'xxd'. Execute `xxd data`. Looking at the bytes '425a 6839' and doing a google search, shows us this is a bzip2 file. Let's rename it to a proper extension, and uncompress.

```
mv data data.bz2
bzip2 -d data.bz2
```

As before we end up with a 'data' file. Let's have a look at it again with 'xxd'. Again the same bytes '1f8b 0808'. Let's rename to '.gz' and uncompress.

```
mv data data.gz
gzip -d data.gz
```

Now the new 'data' file that we got is different, it's much bigger than the previous ones when viewed with 'xxd', let's pipe the output to 'head' command to see just the first 10 lines. `xxd data | head` instead just to see the 1st few lines. With a quick google search we can see this is a tar archive, we can see this by the null padding. Let's unarchive this, with the `tar data` command. This gives us 'data5.bin' file, running the 'xxd' & 'head' command again, will show us it's another tar archive... `tar xf data5.bin` gives us 'data6.bin', which again is a bzip2 compressed file. There is nothing new in this level so keep unarchiving and decompressing till you get to the password.

```
mv data6.bin data6.bz2
bzip2 -d data6.bz2
tar xf data6
mv data8.bin data8.gz
gzip -d data8.gz
cat data8
```

Now use the password to login to Bandit 13.

```
exit
ssh bandit13@bandit.labs.overthewire.org -p 2220
Password: FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
```

References:
[mktemp](https://man7.org/linux/man-pages/man1/mktemp.1.html)
[cp](https://man7.org/linux/man-pages/man1/cp.1.html)
[Backticks & &()](https://www.redhat.com/en/blog/backtick-operator-vs-parens)
[xxd](https://man7.org/linux/man-pages/man1/hexdump.1.html)
[mv](https://man7.org/linux/man-pages/man1/mv.1.html)
[tar](https://man7.org/linux/man-pages/man1/tar.1.html)
[head](https://man7.org/linux/man-pages/man1/head.1.html)

### Bandit 14
Official Tips: [Bandit14](https://overthewire.org/wargames/bandit/bandit14.html)

This level is relatively simple, after login in to Bandit 13 and doing enumeration of the user directory we can see a file called 'sshkey.private'. Checking the file out with 'cat' we can see that it is a private key, file has to start with '-----BEGIN RSA PRIVATE KEY-----'. A private key is part of asymmetric cryptography and is used for decryption, it can also be used for authentication with SSH. Having a look at the official tips we can see this key is used to login to Bandit 14 and we need to get to '/etc/bandit_pass/bandit14'. As localhost ssh sessions are blocked on the host we have to copy over the file to our local machine and than use it to login to next level. We can copy over the file with secure copy 'scp'.

Remember to 'cat' a copy of the /etc/bandit_pass/bandit14, you'll need it in next level!

```
scp -P 2220 bandit13@bandit.labs.overthewire.org:~/sshkey.private ./sshkey.private
```

Now use the password to login to Bandit 14.

```
exit
ssh bandit14@bandit.labs.overthewire.org -p 2220 -i ./sshkey.private
```

References:
[scp](https://man7.org/linux/man-pages/man1/scp.1.html)
[scp examples](https://linuxblog.io/linux-securely-copy-files-using-scp/)
[Symmetric and Asymmetric Key Encryption](https://www.geeksforgeeks.org/computer-networks/difference-between-symmetric-and-asymmetric-key-encryption/)

### Bandit 15
Official Tips: [Bandit15](https://overthewire.org/wargames/bandit/bandit15.html)

This level is about probing ports on the system, the official tips tell us we need to use the password from level 14 and send it to port 30000 on the localhost. The password can be found in the '/etc/bandit_pass/bandit14'. To interact with the port 30000 we can use a tool like telnet, this is a very simple clear text protocol for interacting with a remote server. What we can do is 'telnet localhost 30000' or 'telnet 127.0.0.1 30000', google the difference between localhost and 127.0.0.1 if you don't know ;P. Once we are connected to the port we can type out the password or copy and paste. If you don't wanna type it out, there is also another command we can use called netcat, and user '<' to feed the file to the port.

```
nc localhost 30000 < /etc/bandit_pass/bandit14
```

Now use the password to login to Bandit 15.

```
exit
ssh bandit15@bandit.labs.overthewire.org -p 2220
Password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
```

References:
[localhost](https://en.wikipedia.org/wiki/Localhost)
[telnet](https://man7.org/linux/man-pages/man1/telnet-probe.1.html)
[nc](https://en.wikipedia.org/wiki/Netcat)

### Bandit 16
Official Tips: [Bandit16](https://overthewire.org/wargames/bandit/bandit16.html)

This level is very similar to last one only we have to use port 30001, and the communication has to happen over SSL/TLS, in previous level 'telnet' or 'nc' used a clear text connection meaning the communication was not encrypted. In this level we have to encrypt the connection, we can accomplish this with number of tools but on this system the easiest is to use the 'openssl' command with the 's_client' option.

Once the connection is established, paste in the password from previous level and hit enter.

```
openssl s_client localhost:30001
```

For a quick equivalent of a one liner of the 'nc' command you can use this:

```
openssl s_client -connect localhost:30001 -quiet < /etc/bandit_pass/bandit15

OR

ncat --ssl localhost 30001 < /etc/bandit_pass/bandit15
```

Now use the password to login to Bandit 16.

```
exit
ssh bandit16@bandit.labs.overthewire.org -p 2220
Password: kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
```

References:
[openssl](https://docs.openssl.org/3.3/man1/)

### Bandit 17 [TODO]
Official Tips: [Bandit17](https://overthewire.org/wargames/bandit/bandit17.html)

[Explain]

```
```

Now use the password to login to Bandit 17.

```
exit
ssh bandit17@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 18 [TODO]
Official Tips: [Bandit18](https://overthewire.org/wargames/bandit/bandit18.html)

[Explain]

```
```

Now use the password to login to Bandit 18.

```
exit
ssh bandit18@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 19 [TODO]
Official Tips: [Bandit19](https://overthewire.org/wargames/bandit/bandit19.html)

[Explain]

```
```

Now use the password to login to Bandit 19.

```
exit
ssh bandit19@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 20 [TODO]
Official Tips: [Bandit20](https://overthewire.org/wargames/bandit/bandit20.html)

[Explain]

```
```

Now use the password to login to Bandit 20.

```
exit
ssh bandit20@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 21 [TODO]
Official Tips: [Bandit21](https://overthewire.org/wargames/bandit/bandit21.html)

[Explain]

```
```

Now use the password to login to Bandit 21.

```
exit
ssh bandit21@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 22 [TODO]
Official Tips: [Bandit22](https://overthewire.org/wargames/bandit/bandit22.html)

[Explain]

```
```

Now use the password to login to Bandit 22.

```
exit
ssh bandit22@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 23 [TODO]
Official Tips: [Bandit23](https://overthewire.org/wargames/bandit/bandit23.html)

[Explain]

```
```

Now use the password to login to Bandit 23.

```
exit
ssh bandit23@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 24 [TODO]
Official Tips: [Bandit24](https://overthewire.org/wargames/bandit/bandit24.html)

[Explain]

```
```

Now use the password to login to Bandit 24.

```
exit
ssh bandit24@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 25 [TODO]
Official Tips: [Bandit25](https://overthewire.org/wargames/bandit/bandit25.html)

[Explain]

```
```

Now use the password to login to Bandit 25.

```
exit
ssh bandit25@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 26 [TODO]
Official Tips: [Bandit26](https://overthewire.org/wargames/bandit/bandit26.html)

[Explain]

```
```

Now use the password to login to Bandit 26.

```
exit
ssh bandit26@bandit.labs.overthewire.org -p 2220
Password: 
```

References:
[file](https://man7.org/linux/man-pages/man1/file.1.html)

### Bandit 27 [TODO]
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

### Bandit 28 [TODO]
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

### Bandit 29 [TODO]
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

### Bandit 30 [TODO]
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

### Bandit 31 [TODO]
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

### Bandit 32 [TODO]
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

### Bandit 33 [TODO]
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

