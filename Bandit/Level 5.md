<h2>Task</h2>

The password for this level is stored in the only human-readable file in the inhere directory


<h2>Thoughts</h2>

The first clue to what I should be looking for is this "human-readable" file. This means that the file type that I am looking for is in a text type, also called ASCII text. The ```file``` command allows me to determine the type of a file by passing the file name as an argument: ```file <filename>```
This means I can pass all the files in the ```inhere``` directory through this command and the one that returns an ASCII text type is going to be the file the password is hidden in.

<h2>Solution</h2>

When we use ```ls``` command in the inhere directory we are presented with 10 files: ```-file00``` through ```-file09```

The naming convention of these files allows us to pass the final digit of the filename in braces leveraging brace expansion rather than typing out each file name individually: ```./-file0{0,1,2,3,4,5,6,7,8,9}```

This combined with the file command: ```file ./-file0{0,1,2,3,4,5,6,7,8,9}``` produces an output telling us the file type for each:

    ./-file00: PGP Secret Sub-key -
    ./-file01: data
    ./-file02: data
    ./-file03: data
    ./-file04: data
    ./-file05: data
    ./-file06: data
    ./-file07: ASCII text
    ./-file08: data
    ./-file09: data

From the output we see that ```-file07``` is a ASCII text file, printing the contents of this file will give us our password
