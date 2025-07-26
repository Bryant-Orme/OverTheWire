<h2>Task</h2>

The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it

<h2>Thoughts</h2>

We can use ```nmap``` to scan the ports ```31000 - 32000```, by default it will only return open ports, we can look at the service type of each port to determine if it is using SSL/TLS. Then we can send the password using ```openssl s_client```

<h2>Solution</h2>

Running the command ```nmap -p 31000-32000 localhost``` we see:

    PORT      STATE SERVICE
    31046/tcp open  unknown
    31518/tcp open  unknown
    31691/tcp open  unknown
    31790/tcp open  unknown
    31960/tcp open  unknown

We can try to connect to each port using ```openssl s_client --connect localhost:<port number>```

Port ```31790``` is one of two ports that uses SSL, entering in the password we are given the RSA key for bandit17. Saving this and using it to log into the next level and looking at that levels password under ```/etc/bandit_pass/bandit17``` returns us the password for the next level

  *Note: When I was playing through this level the password for bandit 16 start with a ```k``` which led to a lot of headscratching because I kept getting back ```KEYUPDATE``` from the SSL server. This is because there are a few characters that are reserved as ```CONNECTED COMMANDS``` when communicating with and SSL server, of which ```Q,R,k,K``` are reserved thus it was reading the first character as a command.* 
    
There are a few ways around this:
  
  1. Piping the password into the openSSL command
    
  2. Using the ```-quiet``` tag
