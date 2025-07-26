<h2>Task</h2>

The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption

<h2>Thoughts</h2>

We can use ```openssl s_client``` to connect to a host and send messages that are ssl encrypted, it is similar to ```telnet```

<h2>Solution</h2>

Using ```openssl s_client``` we just need to use to ```-connect``` tag and pass the host and port number in as parameters and this will open an ssl encrypted connection with the host: ```openssl s_client -connect localhost:30001```

Entering in the password for this level once the handshake is complete gives us the password for the next level
