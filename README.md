Darbcoin (DEI)
===========

Darbcoin is this really, really... kind of cryptocoin. It uses scrypt as a proof-of-work algorithm. 3553 Darbcoins are generated approximately every minute, for all time (probably).

How to Build (Linux)
-------


How to Connect
-------
Darbcoin is somewhat lacking in nodes, so you might have to run the client with `-connect=131.215.167.157` to get it to work. You can do this with both the console and graphical clients. Darbcoin uses TCP port 3553, so open that port if you want others to able to connect to you.

How to Mine
-------
You can mine using your CPU with miner built into the client either through the graphical client, or in the console client using the command `setgenerate true [# Threads]`.

To mine with your GPU, create a file called `darbcoin.conf` in `%appdata%/Darbcoin` (Windows) or `~/.darbcoin` (Linux) containing:

    rpcuser=[USERNAME]
    rpcpassword=[PASSWORD]

Then run the Darbcoin client with -server, which will start a JSON-RPC server on port 3552. Then, pick a Litecoin mining application of your choice ([GUIMiner-scrypt](https://bitcointalk.org/index.php?topic=150331.0) works, make sure to set 'Use stratum' to No), and point it to `localhost:3552` with the username and password you specified in `darbcoin.conf`. It should work, hopefully.

License
-------

Darbcoin is released under the terms of the MIT license.
