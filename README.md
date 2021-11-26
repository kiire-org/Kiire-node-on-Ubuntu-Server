# Kiire-node-on-Ubuntu-Server
*Install a node for Kiire on Ubuntu Server 18.04 with the following tutorial*

**Update your Ubuntu server with the following command:**

sudo apt-get update && sudo apt-get upgrade -y

**Install the required dependencies with the following command:**

sudo apt-get install build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils python3 libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-test-dev libboost-thread-dev libboost-all-dev libboost-program-options-dev libminiupnpc-dev libzmq3-dev libprotobuf-dev protobuf-compiler unzip software-properties-common cmake -y

**Install the repository ppa:bitcoin/bitcoin with the following command:**

sudo add-apt-repository ppa:bitcoin/bitcoin

**Confirm the installation of the repository by pressing on the enter key.** 

enter

**Install Berkeley DB with the following command:**

sudo apt-get update && sudo apt-get install libdb4.8-dev libdb4.8++-dev -y

**Download the Linux daemon for your wallet with the following command:**

wget "https://github.com/kiire-org/Linux-daemon/blob/5cdf053a051adebb6d7fea5052e748766afc5f1f/kiire-daemon-linux.tar.gz" -O kiire-daemon-linux.tar.gz

**Extract the tar file with the following command:**

tar -xzvf kiire-daemon-linux.tar.gz

**Download the Linux tools for your wallet with the following command:**

wget "https://github.com/kiire-org/Linux-wallet/blob/e8cd06927e5d597159a5ca587a30610951a3e8cc/kiire-qt-linux.tar.gz" -O kiire-qt-linux.tar.gz

**Extract the tar file with the following command:**

tar -xzvf kiire-qt-linux.tar.gz

**Type the following command to install the daemon and tools for your wallet:**

sudo mv kiired kiire-cli kiire-tx /usr/bin/

**Create the data directory for your coin with the following command:**

mkdir $HOME/.kiire

**Open nano.**

nano $HOME/.kiire/kiire.conf -t

**Paste the following into nano.**

rpcuser=rpc_kiire

rpcpassword=dR2oBQ3K1zYMZQtJFZeAerhWxaJ5Lqeq9J2

rpcbind=0.0.0.0

rpcallowip=127.0.0.1

listen=1

server=1

txindex=1

daemon=1

**Save the file with the keyboard shortcut ctrl + x.**

ctrl + x

**Type the following command to start your node:**

kiired
