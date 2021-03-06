EighthCoin PoS + Masternode
===========================

EighthCoin is a digital currency designed for low fees and instant transactions for payments all around the world and merchants that accept cryptocurrency as a form of payment.


EighthCoin benefits from the open source and transparent nature of Bitcoin, and utilizes a more distributed encryption system known as Staking combined with a reward system for mining. This makes earning rewards more possible from your desktop and resist ASCI machines. EighthCoin is a PoS-based cryptocurrency.



EighthCoin Specifications

Coin name: EighthCoin 

Coin Type :  POS / Masternode

Symbol: 8TH

Address Prefix: 8

Masternode: 800000 coins

Stake Min Age: 8 min

Stake Max Age: 88 Days


Development process
===========================

Developers work in their own trees, then submit pull requests when
they think their feature or bug fix is ready.

The patch will be accepted if there is broad consensus that it is a
good thing.  Developers should expect to rework and resubmit patches
if they don't match the project's coding conventions (see coding.txt)
or are controversial.

The master branch is regularly built and tested, but is not guaranteed
to be completely stable. Tags are regularly created to indicate new
stable release versions of EighthCoin.

Feature branches are created when there are major new features being
worked on by several people.

From time to time a pull request will become outdated. If this occurs, and
the pull is no longer automatically mergeable; a comment on the pull will
be used to issue a warning of closure. The pull will be closed 15 days
after the warning if action is not taken by the author. Pull requests closed
in this manner will have their corresponding issue labeled 'stagnant'.

Issues with no commits will be given a similar warning, and closed after
15 days from their last activity. Issues closed in this manner will be 
labeled 'stale'.

EighthCoin-qt: Qt5 GUI for EighthCoin

Build instructions

Debian

First, make sure that the required packages for Qt5 development of your distribution are installed, for Debian and Ubuntu these are:

sudo apt-get install qt5-default qt5-qmake qtbase5-dev-tools qttools5-dev-tools build-essential 

sudo apt-get install libboost-dev libboost-system-dev libboost-filesystem-dev libboost-program-options-dev libboost-thread-dev libssl-dev 

sudo apt-get install  libdb-dev libdb++-dev

 This Step is needed as well
 
 sudo apt-get install libqt4-dev libminiupnpc-dev
 
then execute the following:

qmake

make

Alternatively, install Qt Creator and open the eighthcoin-qt.pro file.

An executable named eighthcoin-qt will be built.

Windows

Windows build instructions:

Download the QT Windows SDK and install it. You don't need the Symbian stuff, just the desktop Qt.
Compile openssl, boost and dbcxx.
Open the .pro file in QT creator and build as normal (ctrl-B)
Mac OS X

Download and install the Qt Mac OS X SDK. It is recommended to also install Apple's Xcode with UNIX tools.
Download and install MacPorts.
Execute the following commands in a terminal to get the dependencies:
sudo port selfupdate
sudo port install boost db48 miniupnpc
Open the .pro file in Qt Creator and build as normal (cmd-B)
Build configuration options

UPNnP port forwarding

To use UPnP for port forwarding behind a NAT router (recommended, as more connections overall allow for a faster and more stable eighthcoin experience), pass the following argument to qmake:

qmake "USE_UPNP=1"
(in Qt Creator, you can find the setting for additional qmake arguments under "Projects" -> "Build Settings" -> "Build Steps", then click "Details" next to qmake)

This requires miniupnpc for UPnP port mapping. It can be downloaded from http://miniupnp.tuxfamily.org/files/. UPnP support is not compiled in by default.

Set USE_UPNP to a different value to control this:

USE_UPNP=-	no UPnP support, miniupnpc not required;
USE_UPNP=0	(the default) built with UPnP, support turned off by default at runtime;
USE_UPNP=1	build with UPnP support turned on by default at runtime.
Notification support for recent (k)ubuntu versions

To see desktop notifications on (k)ubuntu versions starting from 10.04, enable usage of the FreeDesktop notification interface through DBUS using the following qmake option:

qmake "USE_DBUS=1"
Generation of QR codes

libqrencode may be used to generate QRCode images for payment requests. It can be downloaded from http://fukuchi.org/works/qrencode/index.html.en, or installed via your package manager. Pass the USE_QRCODE flag to qmake to control this:

USE_QRCODE=0	(the default) No QRCode support - libarcode not required
USE_QRCODE=1	QRCode support enabled
Berkely DB version warning

A warning for people using the static binary version of EighthCoin on a Linux/UNIX-ish system (tl;dr: Berkely DB databases are not forward compatible).

The static binary version of EighthCoin is linked against libdb 5.0 (see also this Debian issue).

Now the nasty thing is that databases from 5.X are not compatible with 4.X.

If the globally installed development package of Berkely DB installed on your system is 5.X, any source you build yourself will be linked against that. The first time you run with a 5.X version the database will be upgraded, and 4.X cannot open the new format. This means that you cannot go back to the old statically linked version without significant hassle!

Ubuntu 11.10 warning

Ubuntu 11.10 has a package called 'qt-at-spi' installed by default. At the time of writing, having that package installed causes eighthcoin-qt to crash intermittently. The issue has been reported as launchpad bug 857790, but isn't yet fixed.

Until the bug is fixed, you can remove the qt-at-spi package to work around the problem, though this will presumably disable screen reader functionality for Qt apps:

sudo apt-get remove qt-at-spi



Go to RUN -> %appdata% -> Common Files -> EighthCoin8 -> Open Wallet Configuration File. Open the file in Note and paste the following lines. The Config file is located as EighthCoin.conf


eighthcoin.conf file:

rpcuser=admin

rpcpassword=root

rpcallowip=127.0.0.1

rpcport=8889

port=8888

listen=1

server=1

addnode=35.197.22.150

addnode=35.192.57.222





BASIC MASTERNODE GUIDE FOR WINDOWS
===========================

Open and Run the wallet for the first time. In the lower left hand corner of the User Interface, you will see “Synchronizing with network” and other sync messages each time you open your Wallet. If there is a problem synchronizing, it may say “No Block Source Available” instead. If this happens, just close and re-open the wallet until it synchronizes

Go to Help -> Debug Console.




In the Console window enter "getaccountaddress MN" and copy the result.

This is your MASTERNODE DEPOSIT ADDRESS, where you will deposit the coins to create a masternode.
(Donation Address*)
Pay 800,000 8TH exactly into this address.


In the Console Debug window enter "masternode genkey" and copy the result. This is your MASTERNODE PRIVKEY. This is your MASTERNODE PRIVKEY.
(PrivKey*)
 
 
In the Console Debug window enter "masternode outputs".
{
"a33e0795a9b44d61anbdcd0a1565c9e7c4247a233ca55ae95762f5cbca40ca97" : "0" 
(TxHash*):(Output Index*)
}


Masternodes --> My Master Nodes --> Create
(Alias*) : MN
(Address*) : Your IP:8888
(Donation %) : 100



Click "start". You will see the response “Masternode started successfully”.

Congratulations, your masternode is now running.

Now click the Masternodes tab that is now visible. All masternodes need to be active for a certain amount of blocks before they are recognized by the network and eligible for rewards.









