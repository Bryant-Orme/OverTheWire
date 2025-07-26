<h2>Task</h2>

To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary

<h2>Thoughts</h2>

SetUID allows us to set the idenity of the user, meaning we can effectivly run commands as a different user

<h2>Solution</h2>

Running the ```.bandit20-do``` binary in the homedirectory gives us:

    Run a command as another user.
    Example: ./bandit20-do id
    
Running the example command ```./bandit20-do id``` gives us:

    uid=11019(bandit19) gid=11019(bandit19) euid=11020(bandit20) groups=11019(bandit19)
    
Interesting note here is the EUid which stands for effective user id, which differs from uid in a way that allows us to runs commands as the euid

Checking the priviligies of the ```/etc/bandit_pass/bandit20``` they are all owned by the user ```bandit20```, which means to be able to access them we would have to run the command as ```bandit20```

Using the binary we can run ```./bandit20-do cat /etc/bandit_pass/bandit20``` and this will return us the password for the next level
