<h2>Task</h2>

There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

<h2>Thoughts</h2>

The task tells us that ```suconnect``` creates a connection to localhost and listens for the password to this level, if it receives the correct password it returns the password for the next level.

We will have to setup a 'one-time' server that is able to send the current level's password as a string to anything that tries to connect to it.

Once we setup up this 'server' we can run the ```suconnect``` with the post the 'server' is on and this will return the password for the next level.

<h2>Solution</h2>

To setup the 'one-time' server will have to figure out which ports are open on the localhost. Running ```nmap -r localhost``` 

    PORT      STATE SERVICE
    22/tcp    open  ssh
    1111/tcp  open  lmsocialserver
    1234/tcp  open  hotline
    1840/tcp  open  netopia-vo2
    4321/tcp  open  rwhois
    8000/tcp  open  http-alt
    30000/tcp open  ndmps
    50001/tcp open  unknown

We can setup the server on port ```1234```. To do this we will need to use the ```echo``` command so whenever a connection is made to the port the current levels password is replayed back to the listener.

We can use ```nc``` with ```-l``` to make it so it runs the echo command whenever it hears a new connection to the port we specify using the ```-p``` tag.

Putting this all together, to setup the echo server we can run ```echo 'obfuscated password' | nc -l -p 1234 &``` The ```&``` allows us to run the command in the background so we are still able to use the connection we established and don't have to create a new ssh connection.

We can then run the ```suconnect``` binary pointing to port ```1234``` to get the password for the next level: ```./suconnect 1234```

This produces: 

    Read: 4pIjcunZ0fK2vmp3IwfG8Vf7VhxD6pOA
    Password matches, sending next password
    the obfuscated password
