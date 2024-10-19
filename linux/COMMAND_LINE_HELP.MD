# ACTIVITY:

In this activity we use three different commands `man`, `whatis`, and `apropos`. These commands are meant to help understand other commands, and how they're used.

To begin we'll imagine a scenario where we can't remember what the `cat` command. We can use the `whatis` command followed by whichever command we'd like to get a short summary of(in this case `cat`).

`analyst@ad39b58b7591:~$ whatis cat`

We're given the output:

`cat (1)              - concatenate files and print on the standard output`

If we need more details about `cat`, and all of its options we can use the `man` command:

`man cat`

The man command returns a general description of cat and information about each of its options. You can output more information one line at a time by pressing the ENTER key or output the next page of the manual by pressing the space bar. Press Q to exit the manual page.

Say that you only remember how a command works. you can use the command `apropos` to find a command using keywords. There is no right and wrong when using apropos in terms of keywords. Think of it as a very focused search. It will only return commands that correspond to keywords you supply. Keep trying if the first returned command does not provide what you need. Also, keep in mind that using the -a option will limit results to only those commands that match all keywords supplied.

EXAMPLE:

`apropos -a first part file`

This outputs:

`head (1)             - output the first part of files`

