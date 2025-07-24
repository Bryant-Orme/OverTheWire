<h2>Task</h2>

The password for the next level is stored in the file data.txt next to the word **millionth**


<h2>Thoughts</h2>

We can use the ```grep``` command to search for the word 'millionth' in the data.txt file

<h2>Solution</h2>

To use ```grep``` we just pass in the *pattern* we are looking for as the first argument then the file we want to search through as the second. This would look something like this: ```grep 'millionth' data.txt```

Running this command it returns the line containing our patter and next to it is our password for the next level
