<h2>Task</h2>

The password for this level is stored somewhere on the server and has all of the following properties:

    owned by user bandit7
    owned by group bandit6
    33 bytes in size

<h2>Thoughts</h2>

We can use the find command to search through directories for files that have specific parameters. In this case we will be using the ```-user``` ```-group``` and ```-size``` tags to find our hidden password file

<h2>Solution</h2>

When constructing this command we can use ```-size``` tag to find files that are exactly 33 bytes 

The ```-user``` and ```-group``` tags are both straight forward, we will be passing along the given parameters as arguments

We also want to search across the entire server so we will pass the ```/``` as the first argument into the find command to start its search at the root folder

Putting these all together: ```find / -size 33c -group bandit6 -user bandit7``` returns us a bunch of premission denied errors, we can remove these by sending the errors to a null device file. Thus ```find / -size 33c -group bandit6 -user bandit7 2>/dev/null``` returns us ```/var/lib/dpkg/info/bandit7.password```

Printing out the contents of this file produces: ```an obfuscated password```
