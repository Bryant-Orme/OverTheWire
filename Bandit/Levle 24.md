<h2>Task</h2>

A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.

<h2>Thoughts</h2>

We need to look at the cron that is being run and how determine how this could lead us to the password for the next level.

<h2>Solution</h2>

Running ```cat /etc/cron.d/cronjob_bandit23``` shows us the location for this bash file that is being run ```/usr/bin/cronjob_bandit23.sh```

We can get the contents of the bash file ```cat /usr/bin/cronjob_bandit23.sh``` this produces:

    #!/bin/bash

    myname=$(whoami)
    mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

    echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

    cat /etc/bandit_pass/$myname > /tmp/$mytarget

This bash file is taking the user and creating an obfuscated file which contains the corresponding password for that user (level).

We can get the name of the obfuscated file by running the same commands the script uses ```echo 'I am user bandit23' | md5sum | cut -d ' ' -f 1```

This produces: 8ca319486bfbbc3663ea0fbe81326349

We can the print out the contents of this file ```cat /tmp/8ca319486bfbbc3663ea0fbe81326349``` which produces ```obfuscated password```
