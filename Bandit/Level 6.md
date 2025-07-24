<h2>Task</h2>

The password for this level is stored in a file somewhere under the inhere directory and has all of the following properties:

    human-readable
    1033 bytes in size
    not executable


<h2>Thoughts</h2>

We can use the find command to search through directories for files that have specific parameters. In this case we will be using the ```-readable``` ```-executable``` and ```-size``` tags to find our hidden password file

<h2>Solution</h2>

When constructing this command we can use the basic ```-readable``` tag to return human-readable files. 

In order to return none executable files we will have to use the ```-not``` tag (in my case I used ```\!``` which is equivalent to the ```-not``` tag). 

Lastly the ```-size``` tag, since we know the exact size of the file we just put that after the ```-size``` tag followed by the units of space: ```-size 1033c``` (the c denotes bytes)

    Note: the ```-readable``` and ```-executable``` are realtive to the premission the current user has

Putting these all together: ```find -readable \! -executable -size 1033c``` returns us ```./inhere/maybehere07/.file2```

Printing out the contents of this file produces: ```an obfuscated password```
