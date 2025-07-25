<h2>Task</h2>

The password for the next level is stored in the file data.txt, which contains base64 encoded data

<h2>Thoughts</h2>

The file is base64 encoded which means to decode it we need to use ```-d``` flag on the ```base64``` command and this will return the password

<h2>Solution</h2>

```base64 -d data.txt``` produces: ```obfuscated password```
