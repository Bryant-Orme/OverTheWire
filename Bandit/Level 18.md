<h2>Task</h2>

There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new

<h2>Thoughts</h2>

We can use the ```diff``` command to display the differences between two files

<h2>Solution</h2>

    diff passwords.old passwords.new
    42c42
    < C6XNBdYOkgt5ARXESMKWWOUwBeaIQZ0Y
    ---
    > obfuscated password

  The bottom line is the change that has been made in ```passwords.new```
