Darbcoin (DEI)
===========

Darbcoin is this really, really... kind of cryptocoin. It uses scrypt as a proof-of-work algorithm. 3553 Darbcoins are generated approximately every minute, for all time (probably).

How to Build (for Debian based Linux)
-------
1. Get the dependencies

    sudo apt-get install build-essential libboost-all-dev libcurl4-openssl-dev libdb5.1-dev libdb5.1++-dev qt-sdk libminiupnpc-dev

2. Download the source. For the rest of the steps, we'll assume it's stored in ``~/darbcoin`

3. To build the command-line client (darbcoind):

    cd ~/darbcoin/src
    make -f makefile.unix "USE_UPNP=-"
    
4. To build the graphical client (darbcoin-qt):

    cd ~/darbcoin
    qmake "USE_UPNP=-"
    make

How to Build (Windows)
-------
Don't. It's too hard. Abandon all hope. Use the things compiled using devil voodoo black magic in the `/release` folder.

How to Connect
-------
Darbcoin is somewhat lacking in nodes, so you might have to run the client with `-addnode=darbcoin.myanimelife.net` to get it to work. You can do this with both the command-line and graphical clients. On Windows, just run the `Darbcoin-connect.bat` file, and it'll automatically run Darbcoin with the correct arguments. Darbcoin uses TCP port 3553, so open that port if you want others to able to connect to you.

How to Mine
-------
You can mine using your CPU with miner built into the client either through the graphical client, or in the command-line client using the command `setgenerate true [# Threads]`.

To mine with your GPU, create a file called `darbcoin.conf` in `%appdata%/Darbcoin` (Windows) or `~/.darbcoin` (Linux) containing:

    rpcuser=[USERNAME]
    rpcpassword=[PASSWORD]

Then run the Darbcoin client with -server (this is automatically done in `Darbcoin-connect.bat`), which will start a JSON-RPC server on port 3552. Then, pick a Litecoin mining application of your choice ([GUIMiner-scrypt](https://bitcointalk.org/index.php?topic=150331.0) works, make sure to set 'Use stratum' to No), and point it to `localhost:3552` with the username and password you specified in `darbcoin.conf`. It should work, hopefully.

License
-------

Darbcoin is released under the terms of the MIT license.
