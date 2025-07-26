<h2>Task</h2>

The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost

<h2>Thoughts</h2>

We can use ```telnet``` to communicate with another host

<h2>Solution</h2>

Using the ```telnet``` command we can setup communication with the localhost on port 30000 by ```telnet localhost 30000``` then passing in the password for this level. This gives us a reply from the host giving us the password for the next level
