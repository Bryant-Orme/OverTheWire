<h2>Task</h2>

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost

<h2>Thoughts</h2>

We can use ```telnet``` to communicate with another host

<h2>Solution</h2>

Using the ```telnet``` command we can setup communication with ```localhost``` on port 30000 by running ```telnet localhost 30000```. Once the connection is open we can enter the password for this level. 

The local host will respond with ```Correct! obfuscated password``` and close the connection.
