# How to partcipate
Fork this repo.

Edit the `iguana/m_notary_testnet` file. Add a line with your IP address. 

Edit the `iguana/testnet.json` file. Add your pubkey and name. Edit minsigs value to `#_of_pubkeys / 2`. If it's an odd amount, round down. 

Make a PR with edits to this repo. 

# How to start the notary

Clone this repo.

Install the dependencies
```
sudo apt-get install build-essential pkg-config libc6-dev m4 \
        g++-multilib autoconf libtool ncurses-dev unzip git python \
        zlib1g-dev wget bsdmainutils automake libboost-all-dev \
        libssl-dev libprotobuf-dev protobuf-compiler \
        libqrencode-dev libdb++-dev ntp ntpdate vim software-properties-common \
        curl libevent-dev libcurl4-gnutls-dev libsodium-dev cmake clang
```

You must install nanomsg as well. See https://github.com/KomodoPlatform/komodo/wiki/Installing-Komodo-Manually#install-nanomsg

Start PIZZA, BEER and KMD daemons with `-pubkey=` 

Open p2p ports for each coin. Open port 17711 for iguana. 

Fund `-pubkey=` address on all 3 nodes. Import privkey to all 3 nodes. 

If you need PIZZA or BEER, use the faucets at https://www.atomicexplorer.com/#/faucet/beer and https://www.atomicexplorer.com/#/faucet/pizza or ask in #notarynode channel. 

Create a file named `pubkey.txt` at `~/2019NNtestnet/iguana/pubkey.txt`. Contents should be 
```
pubkey=<pubkey>
```

Create a file named `passphrase.txt` at `~/2019NNtestnet/iguana/passphrase.txt`. Contents should be
```
passphrase=<WIF>
```

Wait until the PR is merged. 

do 
```
cd ~/2019NNtestnet/iguana
./m_notary_testnet
```

# How to restart when new participants are added 

```
pkill -15 iguana
./m_notary_testnet
```
