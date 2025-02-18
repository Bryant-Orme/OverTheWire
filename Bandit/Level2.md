<h2>Task</h2>

The password for this level is stored in a file called '-' in the home directory


<h2>Thoughts</h2>

There are special character that are the linux command line, one of them happens to be the name of file which is used to set flags for commands.

We can enter the path to the file we want to concatenate ie ```./-```

<h2>Solution</h2>

When we use ```ls``` command in the home directory the only file returned is one named '-'

We can print to contents of this file out to the terminal by using the ```cat``` command with the direct path to the file: ```cat ./-```

This produces: ```an obfuscated password```
