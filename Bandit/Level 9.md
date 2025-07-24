<h2>Task</h2>

The password for this level is stored in the file data.txt and is the only line of text that occurs only once

<h2>Thoughts</h2>

We can use the ```uniq``` command to compare adjacent lines to determine if they are matching. We need to make sure that all matching lines are next to each other before we preform this command. To do this we can use the ```sort``` command to sort the text of the file

<h2>Solution</h2>

Sorting the data file: ```sort data.txt```

Determining the number of occurences of each line can be done with the ```-c``` tag on the ```uniq``` command: ```uniq -c```

Lastly we can use ```grep``` to search for the line that only occurs once using the regex: ```'1 '```

Putting this all together requires us to pipe each output into the input for the next so the final command looks like: 
    
    ```sort data.txt | uniq -c | grep '1 '```

This produces our: ```obfuscated password```
