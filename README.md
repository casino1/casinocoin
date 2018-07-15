CasinoCoin Core (fork PIVX) integration/staging repository
======================================


It is recommended [use the shell script](https://github.com/canoproject/canoinstall) to install a CasinoCoin Masternode on a Linux server running Ubuntu 14.04 or 16.04

***

Quick installation of the CasinoCoin daemon under linux. See detailed instructions there [build-unix.md](build-unix.md)

Installation of libraries (using root user):

    add-apt-repository ppa:bitcoin/bitcoin -y
    apt-get update
    apt-get install -y build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils
    apt-get install -y libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev
    apt-get install -y libdb4.8-dev libdb4.8++-dev

Cloning the repository and compiling (use any user with the sudo group):

    cd
    git clone https://github.com/canoproject/CasinoCoin.git
    cd CasinoCoin
    ./autogen.sh
    ./configure
    sudo make install
    cd src
    sudo strip casinocoind
    sudo strip casinocoin-cli
    sudo strip casinocoin-tx
    cd ..

Running the daemon:

    casinocoind 

Stopping the daemon:

    casinocoin-cli stop

Demon status:

    casinocoin-cli getinfo
    casinocoin-cli mnsync status

All binaries for different operating systems, you can download in the releases repository:

https://github.com/canoproject/CasinoCoin/releases

P2P port:  7337, RPC port:  7338
-
Distributed under the MIT software license, see the accompanying file COPYING or http://www.opensource.org/licenses/mit-license.php.
