<h2>Task</h2>

The password for this level is stored in the file data.txt in one of the few human-readable strings, preceeded by several ‘=’ characters.

<h2>Thoughts</h2>

The note of the few human-readable strings means the file is probably not going to be an ASCII text file. We can use the ```file``` command to check this. The ```string``` command can be used to print out printable strins in a file, this can be useful if the file isn't an ASCII text file. The mention of the password being proceeded by several '=' means we should probably search through the output for these sequences of characters, the ```grep``` command is perfect for this pattern matching

<h2>Solution</h2>

The ```strings``` will output to stdout meaning we can pipe this into the ```grep``` command. Putting these together: 
    
    strings data.txt | grep '==='

This a few lines reading 'the password is' ```obfuscated password```
