# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

> >

* show current working directory path - ls <-lists all directories and files
* entering a directory: cd dir
* present working directory:pwd
* go up a dir: cd ..
* cd by itself goes to home dir: cd ~
* creating a directory: mkdir folder_name
* deleting a directory: rmdir dirname
* removes empty directories in the foldeR: rmdir * 
* creating a file using touch command:touch file1 file2 file3 (creates 3 blank files)
* deleting a file (remove): rm f2
* deleting multiple files: rm f* (remove all files that start with the word f) 
* renaming a file (move command):mv f1 fmv  (f1 renamed to fmv) 
* copying a file from one directory to another: cp f3 f3.backup (ls: f3		f3.backup) 
* listing hidden files: ls -a (shows hidden directories)
* finding a file?!?:locate (doesn’t work so well so use the finder. 
* locating the program: Which cal (tells you where the calendar is located, may insert any other program like python 3) 
* history - list commands you have used. 
* List everything in a directory and put it in a file: ls -al /> dir.txt
* sudo commamnds: sudo -s (access root directory, it will ask for password)



---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls`  
`ls -a`  
`ls -l`  
`ls -lh`  
`ls -lah`  
`ls -t`  
`ls -Glp`  



> > 
* ls - lists all directories
* ls -a (List hidden directories) 
* ls -l (gives a long list of everything with columns) 
* la -la (gives long list with hidden) 
* ls -lh (long list , human readable format)
* ls -lah (long list, list hidden, human readable format) 
* ls -t (sort by modification time) 
* ls -Glp (G enable color output, l - list, p-shows link rather than the object it ref) 
* file file_name <-gives files info or attributes


---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

> >
* ls - lS (lists and sorts the files in the directory by size.) 
* ls - r (print reverse order of the files requested) 
* ls -t  (sort by time, newest first)

---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

> > Takes input/arguement from the left and applies the function on the right to each of the elements of the vector(either seperated by spaces or commas). 

Example: 
* The following command created 3 files (1,2,3 without extension) 
* Smeets-MBP:u2 honeybadger4$ printf "1\n2\n3\n" | xargs touch
* creates 3 files. 

Example 2: 
* Smeets-MBP:u2 honeybadger4$ printf "1\n2\n3\n" | xargs rm
* removes the 3


 

