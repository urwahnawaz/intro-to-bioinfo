# Introduction to shell
## Introduction
### Why shell?
- Lots of functionalities while using bioinformatics software via shell.
- Automate repetitive tasks. This makes bioinformatics less boring and also reduces error.
- Accessing remote computer and HPCs is done via shell.
- Reproducible when working in command line rather than in GUI.

## Navigating files and directories
1. `pwd` - print where we are, i.e. current working directory
2. `ls` - list the files in the directory
	- flags `-`
	- `man ls` - you can navigate through the documentation and know the purposes of each flag.

> ## Challenge
> Use the `-l` option for the `ls` command to display more information for each item 
> in the directory. What is one piece of additional information this long format
> gives you that you don't see with the bare `ls` command?

3. `cd` - Change the directory

### Useful tips and tricks 🛠
1. Tab completion: 
	- This can be used for completing the file and directory names
	- This can also be used to complete the command names
2. Shortcut for paths: `~`: home directory, `/`: root directory, `.`: current directory, and `..`: back one level.

## Creating, moving, copying and removing files and directory
### Creating directories
1. `mkdir` command to create a directory
```{bash}
$ mkdir test_directory
$ cd test_directory
$ nano test.txt
```
### Copying files
2. `cp` command to copy files
```{bash}
$ cp test.txt test_copy.txt
$ ls 
```
### Moving/Renaming files
3. `mv` command to move files
```{bash}
$ mkdir backup
$ mv test.txt backup
```
4. `mv` command to rename the files.
```{bash}
$ mv test_copy.txt test_working.txt
```

### Removing files and folders
5. `rm` command to remove files
```{bash}
$ rm test.txt
$ rm backup
```
6. `rm backup` does not work as it is not empty
> ### Challenge
> Can you find a way to remove the backup directory using the documentation for the `rm` command?

### Useful tips and tricks 🛠
3. Wild cards:
	- This can be used to represent any number of any type of characters
	- Very useful while selecting the related files
```{bash}
$ cd data
$ touch test.txt
$ ls *gz # Any files ending with `gz` are displayed  
$ ls *SR # Any files starting with `SR` are displayed
$ ls *508* # Any files with `508` in the filename are displayed
```
4. Command `history`
	- Useful when you want to access the past commands that were executed.
	- `!` followed by command # can be used to execute the command


> ### Exercise
> 1. Make a `tmp_dir` directory
> 2. Copy first two files from the `data` directory to the `backup` directory using wild card
> 3. Remove the `tmp_dir` directory
