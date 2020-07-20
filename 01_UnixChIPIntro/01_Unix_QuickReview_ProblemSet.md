# Unix Basics Quick Review and Problem Set

__Table of Contents__

 * [Quick Review](#quick-review)
 * [Problem Set](#problem-set)

Quick Review
=========================

| command         | description                              |
| --------------- | ---------------------------------------- |
| `ls`            | list directory contents                  |
| `cd`            | change directory                         |
| `mkdir`         | make a directory                         |
| `rm`            | remove, or delete files and directories. Use caution, it is easy to delete more that you want. |
| `head`          | prints the top few lines to the terminal window |
| `tail`          | prints the last few lines to the terminal window |
| `sort`          | sorts the lines                          |
| `uniq`          | prints the unique lines                  |
| `grep`          | filnds the lines that contain a pattern  |
| `wc`            | counts the number of lines, characters and words |
| `mv`            | move files                               |
| `cp`            | copy files                               |
| `date`          | returns the current date and time        |
| `pwd`           | return working directory name            |
| `ssh`           | remote login                             |
| `scp`           | remote secure copy                       |
| `~`             | shortcut for your home directory         |
| `man <command>` | manual page for the command e.g. `man ls` to get the man page for `ls` |





### Useful UNIX command examples to try

**The files you need later in this review are in a folder on your Desktop!**

Let's go to a directory with a lot of files in it and list those files

```bash
cd /bin/
ls
```

__What's the difference between these two commands?__

Try them both!!
```
ls -l
ls -lt
```


__Pipes__ 

You can string more than one command together with a pipe `|` , such that the standard output of the first command is 'piped' into the standard input of the second command.

Try it!!
```
ls -lt | head
```





Problem Set
===========

1. Log into your machine. 

2. What is the full path to your home directory?

3. Go up one directory?
    - How many files does it contain?
    - How many directories?

4. Make a directory called `problemsets`.

5. Navigate into this new directory called problemsets. Verify that you are in the correct directory by using `pwd`.

6. Use `wget` to copy <https://raw.githubusercontent.com/prog4biol/pfb2017/master/files/sequences.nt.fa> from the web into your problemsets directory. If `wget` is not available on your system, use `curl -O` as an alternative.

7. Without using a text editor calculate or report these qualities for the file `sequences.nt.fa`.
  This file can be found here <https://raw.githubusercontent.com/sabrsyed/pfb2017/master/files/sequences.nt.fa>
      - How many lines does this file contain?   
      - How many characters?    (Hint: check out the options of wc)
      - What is the first line of this file?    (Hint: read the man page of head)
      - What are the last 3 lines?    (Hint: read the man page of tail)
      - How many sequences are in the file?    (Hint: use grep) (Note: The start of a sequence is indicated by a `>` character.)    

