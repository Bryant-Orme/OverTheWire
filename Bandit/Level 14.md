<h2>Task</h2>

The password for this level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level

<h2>Thoughts</h2>

We can use the ```scp``` command to transfer data over SSH. We can transfer files from a remote host to our local machine. The format for transferring remote files: ```scp -P [port] [user][@source][:path to file] [target]``` Where the ```source``` is the machine the file is on and ```target``` is the location we want to transfer the file to.

We ssh into a host using the ```sshkey.private``` as the identity file using the ```-i``` tag. 

The ```sshkey.private``` found in this level can be used to log into the next level. To get the key to our local machine we will need to use ```scp``` to transfer the file to our local copy, then pass the ```sshkey.private``` using the ```-i``` tag.

<h2>Solution</h2>

From local machine:

Running ```scp -P 2220 bandit13@bandit.labs.overthewire.org:sshkey.private ~/Documents``` transfers the ```sshkey.private``` to our machine in the ```/Documents``` directory.

When trying to use the key ```ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220``` we get a warning stating ```Permissions 0640 for 'sshkey.private' are too open``` We need to update the premissions of the key to be more secure. We can use ```chmod``` to change the permissions so that only the owner has priviliges to interact with the file ```chmod 700 sshkey.private```. Rerunning ```ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220``` successfully logs us into the next level.

We can print the password for this level by using ```cat /etc/bandit_pass/bandit14```

This produces: ```an obfuscated password```
