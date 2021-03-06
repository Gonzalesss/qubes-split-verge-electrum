# qubes-split-verge-electrum
Isolate your private keys in a offline VM (cold storage) in Qubes OS

## Create a cold/offline wallet

1. Clone the Debian template by running **qvm-clone debian-8 debian-8-xvg** in dom0
2. Run the debian-8-xvg template and download the Verge Electrum wallet 
https://github.com/vergecurrency/electrum-xvg-tor#1a-getting-started-with-ubuntulinux

3. Create a new AppVM by running **qvm-create -t debian-8-xvg -l black offline-verge** and **qvm-prefs -s offline-xvg netvm none** in dom0
4. Run the offline-xvg AppVM and create a new wallet


## Create a watch-only wallet

1. Create a AppVM with the debian-8-xvg template by running **qvm-create -t debian-8-xvg -l green watching-xvg** and **qvm-prefs -s watching-xvg netvm sys-whonix** in dom0
2. Run the watching-xvg AppVM and create a **watch-only** wallet by importing the public keys from the offline-xvg AppVM


### Important
The private keys should **never** leave the offline-xvg AppVM.
If you want to send your Verge, you should create a new AppVM using the debian-8-xvg template, create a wallet with your existing seeds from the offline wallet.
**Note:** Delete this AppVM after sending your coins.
