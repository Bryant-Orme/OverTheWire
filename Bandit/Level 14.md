<h2>Task</h2>

The password for this level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level

<h2>Thoughts</h2>

We can use the private SSH Key to log into the next level by passing ```sshkey.private``` as the idenitiy file using the ```-i``` tag

<h2>Solution</h2>

```ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220``` logs us into bandit14 and then we can print out the password file for this level using: ```cat /etc/bandit_pass/bandit14```
