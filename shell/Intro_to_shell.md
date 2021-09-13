# Introduction to shell
## Introduction
### Why shell?
- lots of functionalities
- Automate repetitive tasks - thus makes bioinformatics less boring - reduces error
- Accessing remote computer
- Reproducible when working in command line rather that GUI

### Accessing shell
- Mac or Linux machine: Access via Terminal
- Windows: Access via PuTTy
	- IP address `ec2-user@203.101.228.128` and PW: `******`
	- SSH - `22`
	- Press `Open`
## Navigating files and directories
- `pwd` - print where we are, i.e. current working directory
- `ls` - flags `-`
	- `man ls` - you can navigate through the documentation and know the purposes of each flags.
	- Exercise: Use the `-l` option for the `ls` command to display more information for each item in the directory. What is one piece of additional information this long format gives you that you don’t see with the bare `ls` command?
		- Answer: The additional information given includes the name of the owner of the file, when the file was last modified, and whether the current user has permission to read and write to the file.
	- Shortcut: Tab Completion 
		- Makes you more efficient
		- autocomplete the name of the command or the directories

> ## Challenge
> Use the `-l` option for the `ls` command to display more information for each item 
> in the directory. What is one piece of additional information this long format
> gives you that you don't see with the bare `ls` command?
>
> > ## Solution
> > ~~~
> > $ ls -l
> > ~~~
> > 
> > ~~~
> > total 8
> > drwxr-x--- 2 dcuser dcuser 4096 Jul 30  2015 sra_metadata
> > drwxr-xr-x 2 dcuser dcuser 4096 Nov 15  2017 untrimmed_fastq
> > ~~~
> > 
> > The additional information given includes the name of the owner of the file,
> > when the file was last modified, and whether the current user has permission
> > to read and write to the file.



- `cd` - Change the directory

#### Creating, moving, copying and removing files and directory
##### Creating directories
- `mkdir` command to create a directory
```{bash}
$ mkdir test_directory
$ cd test_directory
$ nano test.txt
```
##### Copying files
Use `cp` command to copy files
```{bash}
$ cp test.txt test_copy.txt
$ ls 
```
##### Moving/Renaming files
You can use `mv` command to move files
```{bash}
$ mkdir backup
$ mv test.txt backup
```
You can use the same command to rename the files.
```{bash}
$ mv test_copy.txt test_working.txt
```

#### Removing files and folders
- You can use `rm` command to remove files
```{bash}
$ rm test.txt
$ rm backup
```
- `rm backup` does not work as it is not empty
> ##### Challenge
> Can you find a way to remove the backup directory using documentation for the `rm` command?

### Useful tips and tricks
- Tab completion: 
	- This can be used for completing the file and directory names
	- This can also be used to complete the command names
- Wild cards:
	- This can be used to represent any number of any type of characters
	- Very useful while selecting the related files
```{bash}
$ cd data
$ touch test.txt
$ ls *gz # Any files ending with `gz` are displayed  
$ ls *SR # Any files starting with `SR` are displayed
$ ls *508* # Any files with `508` in the filename are displayed
```

- Full vs relative path `~`: home directory and `/`: root directory  and `.`: current directory, `..`: back one level
- Command history
	- `history` Useful when you want to access the past commands that were execute
	- `!` followed by command # can be used to execute the command


> ### Exercise
> 1. Make a `tmp_dir` directory
> 2. Copy first two files from the `data` directory to the `backup` directory using wild card
> 3. Remove the `tmp_dir` directory
