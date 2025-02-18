<h2>Task</h2>

The password for this level is stored in a file called readme in the home directory


<h2>Thoughts</h2>

We are told there is a file called readme in the home directory. When we login into this level we are in the home directory so we can use the ```ls``` command to list the files in the current directory: ```bandit0@bandit:~$ ls```

We can then use the ```cat``` command to concatenate the contents of the file: ```cat <file>```

<h2>Solution</h2>

When we use ```ls``` command in the home directory the only file returned is one named 'readme'

We can print to contents of this file out to the terminal by using the ```cat``` command: ```cat readme```

This produces: ```The password you are looking for is: obfuscated password```
