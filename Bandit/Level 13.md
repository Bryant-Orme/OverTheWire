<h2>Task</h2>

The password for this level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed

<h2>Thoughts</h2>

The data.txt file is the hex dump of a bunch of compressed files. Using the ```file``` command after each decompression will tell us the decompression algorithm we need to use to get the next until we have the password

<h2>Solution</h2>

Hex dump (```xxd```) -> gzip -> bzip2 -> gzip -> tar -> tar -> bzip2 -> tar -> gzip -> ASCII text file
