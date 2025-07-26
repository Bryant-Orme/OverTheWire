<h2>Task</h2>

The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

<h2>Thoughts</h2>

In the same command line that we use to ```ssh``` into the bandit 18 level, we can pass along commands to be run immediately upon us logging in. Since we know the name of the file and location of the file and we are already logging into the directory where the file is stored we can just ```cat``` the file out upon login, before the ```.bashrc``` can log us out

<h2>Solution</h2>

```ssh bandit18@bandit.labs.overthewire.org -p 2220 'cat readme'``` after entering the password, the contents of the ```readme``` file are printed out and then we are logged out
