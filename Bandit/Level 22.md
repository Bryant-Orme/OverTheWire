<h2>Task</h2>

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

<h2>Thoughts</h2>

We need to look at the cron that is being run and determine what it command(s) it is running and how this could lead us to the password for the next level.

<h2>Solution</h2>

Changing into the ```cd etc/cron.d/``` directory we see ```cronjob_bandit22```

Running ```cat cronjob_bandit22``` on this shows us the location of where the cron is stored ```/usr/bin/cronjob_bandit22.sh```

We can then ```cat /usr/bin/cronjob_bandit22.sh``` to get the output of the bash file that is being run.

This produces:

    #!/bin/bash
    chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
    cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv

This bash file is creating a temp file and using the ```cat``` command to insert the password of bandit22 into the contents of this file.

It is also setting the permissions on this new file so 'others' have read access, meaning we can ```cat``` the contents of this file to get the password for the next level.

Doing this ```cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv``` produces ```obfuscated password```
