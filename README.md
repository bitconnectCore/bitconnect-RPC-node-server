# bitconnect-Linux-Server

bitconnect BlockChain Daemon RPC Server For Cloud-Nodes, Apps, Bots And Explorers

In linux bash, possibly peices together releases from:

https://github.com/bitconnectCore/bitconnect-blockchain-peers

https://github.com/bitconnectCore/bitconnectCoin-blockchain-bootstrap

Has howto build writeup, but also includes static linux ~18.04 release for easiness.

Includes daemon commands and .conf options, Example: server=1 with peers.


## Quick Notes

Non precise deps:
sudo apt-get install build-essential libssl-dev libdb++-dev libboost-all-dev libqrencode-dev miniupnpc libminiupnpc-dev autoconf pkg-config libtool autotools-dev libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools libprotobuf-dev automake -y


**Part1 (build levelDB):**

cd bitconnect/src/leveldb

chmod +x build_detect_platform

make libleveldb.a libmemenv.a


**Part2 (build daemon):**

sudo make -f makefile.unix | sudo make -f makefile.unix PIE=1 STATIC=1


**Part3 (make configuration file):**

cd
sudo nano .bitconnect/bitconnect.conf


**Part4 (configuartion file settings):**

rpcuser=

rpcpassword=

listen=

daemon=

server=

txindex=

rpcport=


**Part5 (start daemon):**

cd bitconnect/src

chmod +x bitconnectd

./bitconnectd start
