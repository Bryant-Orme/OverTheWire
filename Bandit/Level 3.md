<h2>Task</h2>

The password for this level is stored in a file called **spaces in the filename** in the home directory


<h2>Thoughts</h2>

When strings are entered after a command seperated by spaces they are treated as multiple arguments. Thus if a file has spaces in the name we have to pass the <filename> in quotes ``` '' or "" ``` so it gets treated as one argument and not multiple
We can enter the name of the file we want to concatenate ie ```"<filename>" or '<filename>'```

<h2>Solution</h2>

When we use ```ls``` command in the home directory the only file returned is one named 'spaces in the filename'

We can print to contents of this file out to the terminal by using the ```cat``` command with the filename in quotes: ```cat "spaces in the filename"```

This produces: ```an obfuscated password```
