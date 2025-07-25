<h2>Task</h2>

The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

<h2>Thoughts</h2>

The file is using an old encryption method known as rotate 13. We can decrypt this by using the ```tr``` command to translate the characters back to their original message. To do this we first want to break the characters into regex sequences: ```A-M N-Z``` and ```a-m n-z```

Then the second argument that goes into the command is what we want to translate them to ```N-Z A-M``` and ```n-z a-m```

<h2>Solution</h2>

The translate command takes an input from standard input so we need to pipe the contents of data.txt into the translate command: ```cat data.txt | tr 'A-MN-Za-mn-z' 'N-ZA-Mn-za-m'```. This gives us the password
