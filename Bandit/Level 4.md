<h2>Task</h2>

The password for this next level is stored in a hidden file in the inhere directory

<h2>Thoughts</h2>

 To create hidden files in linux you prefix them with a dot ```.```: ```.<filename>```. These files can still be accessed if you know the name of the hidden file but you must include the dot before the name to access it


<h2>Solution</h2>

We can us the ```cd``` command to change directories: ```cd inhere```

Then to list all contents of of directory we can use the -a flag: ```ls -a```
This shows us a hidden file called ```...Hiding-from-you```

We can print the contents of the file with the cat command: ```cat ...Hiding-from-you```

This produces: ```an obfuscated password```
