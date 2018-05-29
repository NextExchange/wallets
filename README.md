mkdir ~/wallets

#--------------------- SYS ----------------------

cd ~/wallets
git clone https://github.com/syscoin/syscoin2
cd syscoin2
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.syscoin
echo "server=1" >> ~/.syscoin/syscoin.conf
echo "listen=0" >> ~/.syscoin/syscoin.conf
echo "listenonion=0" >> ~/.syscoin/syscoin.conf
echo "rpcuser=bartersys" >> ~/.syscoin/syscoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.syscoin/syscoin.conf
chmod 0600 ~/.syscoin/syscoin.conf
syscoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"SYS\"}"

#--------------------- MAC ----------------------

cd ~/wallets
git clone https://github.com/machinecoin-project/machinecoin-core
cd machinecoin-core
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.machinecoin
echo "server=1" >> ~/.machinecoin/machinecoin.conf
echo "listen=0" >> ~/.machinecoin/machinecoin.conf
echo "listenonion=0" >> ~/.machinecoin/machinecoin.conf
echo "rpcuser=bartermac" >> ~/.machinecoin/machinecoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.machinecoin/machinecoin.conf
chmod 0600 ~/.machinecoin/machinecoin.conf
machinecoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"MAC\"}"

#--------------------- FAIR ----------------------

cd ~/wallets
git clone https://github.com/faircoin/faircoin
cd faircoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.faircoin2
echo "server=1" >> ~/.faircoin2/faircoin.conf
echo "listen=0" >> ~/.faircoin2/faircoin.conf
echo "listenonion=0" >> ~/.faircoin2/faircoin.conf
echo "rpcuser=barterfair" >> ~/.faircoin2/faircoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.faircoin2/faircoin.conf
chmod 0600 ~/.faircoin2/faircoin.conf
faircoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"FAIR\"}"

#--------------------- XRE ----------------------

cd ~/wallets
git clone https://github.com/RevolverCoin/revolvercoin
cd revolvercoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.revolvercoin
echo "server=1" >> ~/.revolvercoin/revolvercoin.conf
echo "listen=0" >> ~/.revolvercoin/revolvercoin.conf
echo "listenonion=0" >> ~/.revolvercoin/revolvercoin.conf
echo "rpcuser=barterxre" >> ~/.revolvercoin/revolvercoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.revolvercoin/revolvercoin.conf
chmod 0600 ~/.revolvercoin/revolvercoin.conf
revolvercoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"XRE\"}"

#--------------------- TRC ----------------------

cd ~/wallets
git clone https://github.com/clockuniverse/terracoin
cd terracoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.terracoin
echo "server=1" >> ~/.terracoin/terracoin.conf
echo "listen=0" >> ~/.terracoin/terracoin.conf
echo "listenonion=0" >> ~/.terracoin/terracoin.conf
echo "rpcuser=bartertrc" >> ~/.terracoin/terracoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.terracoin/terracoin.conf
chmod 0600 ~/.terracoin/terracoin.conf
terracoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"TRC\"}"

#--------------------- ZET ----------------------

# default rpcport collides with other wallet, so changed
# {\"coin\":\"ZET\", \"name\":\"zetacoin\", \"pubtype\":80, \"p2shtype\":9,\"rpcport\":11111, \"wiftype\":224, \"txfee\":10000}

cd ~/wallets
git clone https://github.com/zetacoin/zetacoin
cd zetacoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.zetacoin
echo "server=1" >> ~/.zetacoin/zetacoin.conf
echo "listen=0" >> ~/.zetacoin/zetacoin.conf
echo "rpcuser=barterzet" >> ~/.zetacoin/zetacoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.zetacoin/zetacoin.conf
chmod 0600 ~/.zetacoin/zetacoin.conf
zetacoind -rpcport=11111 -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ZET\"}"

#--------------------- FLO ----------------------

cd ~/wallets
git clone https://github.com/florincoin/florincoin
cd florincoin
./autogen.sh
CC=gcc-5 CXX=g++-5 CPP=cpp-5 ./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.florincoin
echo "server=1" >> ~/.florincoin/florincoin.conf
echo "listen=0" >> ~/.florincoin/florincoin.conf
echo "rpcuser=barterflo" >> ~/.florincoin/florincoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.florincoin/florincoin.conf
chmod 0600 ~/.florincoin/florincoin.conf
florincoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"FLO\"}"

#--------------------- EMC2 ----------------------

cd ~/wallets
git clone https://github.com/emc2foundation/einsteinium -b 0.14_dev_HashUnlimited
cd einsteinium
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.einsteinium
echo "server=1" >> ~/.einsteinium/einsteinium.conf
echo "listen=0" >> ~/.einsteinium/einsteinium.conf
echo "listenonion=0" >> ~/.einsteinium/einsteinium.conf
echo "rpcuser=barteremc2" >> ~/.einsteinium/einsteinium.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.einsteinium/einsteinium.conf
chmod 0600 ~/.einsteinium/einsteinium.conf
einsteiniumd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"EMC2\"}"

#--------------------- HODLC ----------------------

# coin symbol changed from HODL to HODLC because of collision with an asset
# default rpcport collides with other wallet, so changed
# {\"coin\":\"HODLC\",\"name\":\"hodlcoin\",\"rpcport\":12989,\"pubtype\":40,\"p2shtype\":5,\"wiftype\":168,\"txfee\":5000}

cd ~/wallets
git clone https://github.com/HOdlcoin/HOdlcoin
cd HOdlcoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.hodlcoin
echo "server=1" >> ~/.hodlcoin/hodlcoin.conf
echo "listen=0" >> ~/.hodlcoin/hodlcoin.conf
echo "rpcuser=barterhodl" >> ~/.hodlcoin/hodlcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.hodlcoin/hodlcoin.conf
chmod 0600 ~/.hodlcoin/hodlcoin.conf
hodlcoind -daemon -rpcport=12989

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"HODLC\"}"

#--------------------- BDL ----------------------

# default rpcport collides with other wallet, so changed
# {\"coin\":\"BDL\",\"name\":\"bitdeal\",\"rpcport\":11332,\"pubtype\":38,\"p2shtype\":5,\"wiftype\":176,\"txfee\":100000}

cd ~/wallets
git clone https://github.com/bitdeal/bitdeal
cd bitdeal
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.bitdeal
echo "server=1" >> ~/.bitdeal/bitdeal.conf
echo "listen=0" >> ~/.bitdeal/bitdeal.conf
echo "listenonion=0" >> ~/.bitdeal/bitdeal.conf
echo "rpcuser=barterbdl" >> ~/.bitdeal/bitdeal.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.bitdeal/bitdeal.conf
chmod 0600 ~/.bitdeal/bitdeal.conf
bitdeald -daemon -rpcport=11332

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"BDL\"}"

#--------------------- BTX ----------------------

cd ~/wallets
git clone https://github.com/LIMXTEC/BitCore
cd BitCore
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.bitcore
echo "server=1" >> ~/.bitcore/bitcore.conf
echo "listen=0" >> ~/.bitcore/bitcore.conf
echo "listenonion=0" >> ~/.bitcore/bitcore.conf
echo "rpcuser=barterbtx" >> ~/.bitcore/bitcore.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.bitcore/bitcore.conf
chmod 0600 ~/.bitcore/bitcore.conf
bitcored -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"BTX\"}"

#--------------------- HUC ----------------------

cd ~/wallets
git clone https://github.com/chronokings/huntercore -b 0.13
cd huntercore
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.huntercoin
echo "server=1" >> ~/.huntercoin/huntercoin.conf
echo "listen=0" >> ~/.huntercoin/huntercoin.conf
echo "listenonion=0" >> ~/.huntercoin/huntercoin.conf
echo "rpcuser=barterhuc" >> ~/.huntercoin/huntercoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.huntercoin/huntercoin.conf
chmod 0600 ~/.huntercoin/huntercoin.conf
huntercoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"HUC\"}"

#--------------------- DGB ----------------------

cd ~/wallets
git clone https://github.com/digibyte/digibyte
cd digibyte
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.digibyte
echo "server=1" >> ~/.digibyte/digibyte.conf
echo "listen=0" >> ~/.digibyte/digibyte.conf
echo "listenonion=0" >> ~/.digibyte/digibyte.conf
echo "rpcuser=barterdgb" >> ~/.digibyte/digibyte.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.digibyte/digibyte.conf
chmod 0600 ~/.digibyte/digibyte.conf
digibyted -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"DGB\"}"

#--------------------- 888 ----------------------

cd ~/wallets
git clone https://github.com/octocoin-project/octocoin
cd octocoin
./autogen.sh
CC=gcc-5 CXX=g++-5 CPP=cpp-5 ./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.octocoin
echo "server=1" >> ~/.octocoin/octocoin.conf
echo "listen=0" >> ~/.octocoin/octocoin.conf
echo "rpcuser=barter888" >> ~/.octocoin/octocoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.octocoin/octocoin.conf
chmod 0600 ~/.octocoin/octocoin.conf
octocoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"888\"}"

#--------------------- MOON ----------------------

cd ~/wallets
git clone https://github.com/mooncoindev/mooncoin
cd mooncoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.Mooncoin
echo "server=1" >> ~/.Mooncoin/Mooncoin.conf
echo "listen=0" >> ~/.Mooncoin/Mooncoin.conf
echo "rpcuser=bartermoon" >> ~/.Mooncoin/Mooncoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.Mooncoin/Mooncoin.conf
chmod 0600 ~/.Mooncoin/Mooncoin.conf
Mooncoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"MOON\"}"

#--------------------- CREA ----------------------

cd ~/wallets
git clone https://github.com/creativechain/creativechain-core
cd creativechain-core
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.creativecoin
echo "server=1" >> ~/.creativecoin/creativecoin.conf
echo "listen=0" >> ~/.creativecoin/creativecoin.conf
echo "listenonion=0" >> ~/.creativecoin/creativecoin.conf
echo "rpcuser=bartercrea" >> ~/.creativecoin/creativecoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.creativecoin/creativecoin.conf
chmod 0600 ~/.creativecoin/creativecoin.conf
creativecoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"CREA\"}"

#--------------------- NMC ----------------------

cd ~/wallets
git clone https://github.com/namecoin/namecoin-core
cd namecoin-core
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.namecoin
echo "server=1" >> ~/.namecoin/namecoin.conf
echo "listen=0" >> ~/.namecoin/namecoin.conf
echo "listenonion=0" >> ~/.namecoin/namecoin.conf
echo "rpcuser=barternmc" >> ~/.namecoin/namecoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.namecoin/namecoin.conf
chmod 0600 ~/.namecoin/namecoin.conf
namecoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"NMC\"}"

#--------------------- BTA ----------------------

cd ~/wallets
git clone https://github.com/BTA-BATA/BATA-SOURCE
cd BATA-SOURCE
chmod 755 autogen.sh
./autogen.sh
CC=gcc-5 CXX=g++-5 CPP=cpp-5 ./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.bata
echo "server=1" >> ~/.bata/bata.conf
echo "listen=0" >> ~/.bata/bata.conf
echo "rpcuser=barterbta" >> ~/.bata/bata.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.bata/bata.conf
chmod 0600 ~/.bata/bata.conf
batad -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"BTA\"}"

#--------------------- ERC ----------------------

cd ~/wallets
git clone https://github.com/LIMXTEC/Europecoin-V3
cd Europecoin-V3
chmod 755 autogen.sh
chmod 755 share/genbuild.sh
chmod 755 src/leveldb/build_detect_platform
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.europecoin
echo "server=1" >> ~/.europecoin/europecoin.conf
echo "listen=0" >> ~/.europecoin/europecoin.conf
echo "rpcuser=bartererc" >> ~/.europecoin/europecoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.europecoin/europecoin.conf
chmod 0600 ~/.europecoin/europecoin.conf
europecoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ERC\"}"

#--------------------- SXC ----------------------

cd ~/wallets
git clone https://github.com/sexcoin-project/sexcoin
cd sexcoin
./autogen.sh
CC=gcc-5 CXX=g++-5 CPP=cpp-5 ./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.sexcoin
echo "server=1" >> ~/.sexcoin/sexcoin.conf
echo "listen=0" >> ~/.sexcoin/sexcoin.conf
echo "rpcuser=bartersex" >> ~/.sexcoin/sexcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.sexcoin/sexcoin.conf
chmod 0600 ~/.sexcoin/sexcoin.conf
sexcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"SXC\"}"

#--------------------- NAV ---------------------

cd ~/wallets
git clone https://github.com/NAVCoin/navcoin-core
cd navcoin-core
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.navcoin4
echo "server=1" >> ~/.navcoin4/navcoin.conf
echo "listen=0" >> ~/.navcoin4/navcoin.conf
echo "listenonion=0" >> ~/.navcoin4/navcoin.conf
echo "rpcuser=barternav" >> ~/.navcoin4/navcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.navcoin4/navcoin.conf
chmod 0600 ~/.navcoin4/navcoin.conf
navcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"NAV\"}"

#--------------------- SMC ----------------------

cd ~/wallets
git clone https://github.com/psionin/smartcoin
cd smartcoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.smartcoin
echo "server=1" >> ~/.smartcoin/smartcoin.conf
echo "listen=0" >> ~/.smartcoin/smartcoin.conf
echo "rpcuser=bartersmc" >> ~/.smartcoin/smartcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.smartcoin/smartcoin.conf
chmod 0600 ~/.smartcoin/smartcoin.conf
smartcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"SMC\"}"

#--------------------- DOGE ----------------------

cd ~/wallets
git clone https://github.com/dogecoin/dogecoin -b v1.10.0
cd dogecoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.dogecoin
echo "server=1" >> ~/.dogecoin/dogecoin.conf
echo "listen=0" >> ~/.dogecoin/dogecoin.conf
echo "rpcuser=barterdoge" >> ~/.dogecoin/dogecoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.dogecoin/dogecoin.conf
chmod 0600 ~/.dogecoin/dogecoin.conf
dogecoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"DOGE\"}"

#--------------------- SIB ----------------------

cd ~/wallets
git clone https://github.com/ivansib/sibcoin
cd sibcoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.sibcoin
echo "server=1" >> ~/.sibcoin/sibcoin.conf
echo "listen=0" >> ~/.sibcoin/sibcoin.conf
echo "listenonion=0" >> ~/.sibcoin/sibcoin.conf
echo "litemode=1" >> ~/.sibcoin/sibcoin.conf
echo "rpcuser=bartersib" >> ~/.sibcoin/sibcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.sibcoin/sibcoin.conf
chmod 0600 ~/.sibcoin/sibcoin.conf
sibcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"SIB\"}"

#--------------------- I0C ----------------------

cd ~/wallets
git clone https://github.com/domob1812/i0coin -b 0.12
cd i0coin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.i0coin
echo "server=1" >> ~/.i0coin/i0coin.conf
echo "listen=0" >> ~/.i0coin/i0coin.conf
echo "listenonion=0" >> ~/.i0coin/i0coin.conf
echo "rpcuser=barteri0c" >> ~/.i0coin/i0coin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.i0coin/i0coin.conf
chmod 0600 ~/.i0coin/i0coin.conf
i0coind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"I0C\"}"

#--------------------- GLT ----------------------

cd ~/wallets
git clone https://github.com/globaltoken/globaltoken
cd globaltoken
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.globaltoken
echo "server=1" >> ~/.globaltoken/globaltoken.conf
echo "listen=0" >> ~/.globaltoken/globaltoken.conf
echo "listenonion=0" >> ~/.globaltoken/globaltoken.conf
echo "rpcuser=barterglt" >> ~/.globaltoken/globaltoken.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.globaltoken/globaltoken.conf
chmod 0600 ~/.globaltoken/globaltoken.conf
globaltokend -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"GLT\"}"

#--------------------- XMY ----------------------

cd ~/wallets
git clone https://github.com/myriadteam/myriadcoin
cd myriadcoin
./autogen.sh
CFLAGS="-O2 -fPIC -DUSE_SSE2" CPPFLAGS="-O2 -fPIC -DUSE_SSE2" ./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.myriadcoin
echo "server=1" >> ~/.myriadcoin/myriadcoin.conf
echo "listen=0" >> ~/.myriadcoin/myriadcoin.conf
echo "rpcuser=barterxmy" >> ~/.myriadcoin/myriadcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.myriadcoin/myriadcoin.conf
chmod 0600 ~/.myriadcoin/myriadcoin.conf
myriadcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"XMY\"}"

#--------------------- ZCL ----------------------

cd ~/wallets
git clone https://github.com/z-classic/zclassic
cd zclassic
./zcutil/build.sh --disable-tests -j4
sudo cp src/zcashd /usr/local/bin/zclassicd
sudo cp src/zcash-cli /usr/local/bin/zclassic-cli
sudo cp src/zcash-tx /usr/local/bin/zclassic-tx
mkdir ~/.zclassic
echo "server=1" >> ~/.zclassic/zclassic.conf
echo "listen=0" >> ~/.zclassic/zclassic.conf
echo "listenonion=0" >> ~/.zclassic/zclassic.conf
echo "rpcuser=barterzcl" >> ~/.zclassic/zclassic.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.zclassic/zclassic.conf
chmod 0600 ~/.zclassic/zclassic.conf
zclassicd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ZCL\"}"

#--------------------- ZER ----------------------

cd ~/wallets
git clone https://github.com/zerocurrency/zero
cd zero
./zcutil/build.sh --disable-rust -j4
sudo cp src/zcashd /usr/local/bin/zerod
sudo cp src/zcash-cli /usr/local/bin/zero-cli
sudo cp src/zcash-tx /usr/local/bin/zero-tx
mkdir ~/.zero
echo "server=1" >> ~/.zero/zero.conf
echo "listen=0" >> ~/.zero/zero.conf
echo "listenonion=0" >> ~/.zero/zero.conf
echo "rpcuser=barterzer" >> ~/.zero/zero.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.zero/zero.conf
echo "addnode=35.164.216.74" >> ~/.zero/zero.conf
echo "addnode=94.176.235.178" >> ~/.zero/zero.conf
chmod 0600 ~/.zero/zero.conf
zerod -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ZER\"}"

#--------------------- DASH ---------------------

cd ~/wallets
git clone https://github.com/dashpay/dash -b v0.12.2.x
cd dash
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.dashcore
echo "server=1" >> ~/.dashcore/dash.conf
echo "litemode=1" >> ~/.dashcore/dash.conf
echo "listen=0" >> ~/.dashcore/dash.conf
echo "listenonion=0" >> ~/.dashcore/dash.conf
echo "rpcuser=barterdash" >> ~/.dashcore/dash.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.dashcore/dash.conf
chmod 0600 ~/.dashcore/dash.conf
dashd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"DASH\"}"

#--------------------- LTC ----------------------

cd ~/wallets
git clone https://github.com/litecoin-project/litecoin
cd litecoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.litecoin
echo "server=1" >> ~/.litecoin/litecoin.conf
echo "listen=0" >> ~/.litecoin/litecoin.conf
echo "listenonion=0" >> ~/.litecoin/litecoin.conf
echo "rpcuser=barterltc" >> ~/.litecoin/litecoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.litecoin/litecoin.conf
chmod 0600 ~/.litecoin/litecoin.conf
litecoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"LTC\"}"

#--------------------- CRW ----------------------

cd ~/wallets
git clone https://github.com/crowndev/crowncoin
cd crowncoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.crown
echo "server=1" >> ~/.crown/crown.conf
echo "litemode=1" >> ~/.crown/crown.conf
echo "listen=0" >> ~/.crown/crown.conf
echo "rpcuser=bartercrw" >> ~/.crown/crown.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.crown/crown.conf
chmod 0600 ~/.crown/crown.conf
crownd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"CRW\"}"

#--------------------- MUE ----------------------

cd ~/wallets
git clone https://github.com/muecoin/MUECore
cd MUECore
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.muecore
echo "server=1" >> ~/.muecore/mue.conf
echo "litemode=1" >> ~/.muecore/mue.conf
echo "listen=0" >> ~/.muecore/mue.conf
echo "listenonion=0" >> ~/.muecore/mue.conf
echo "rpcuser=bartermue" >> ~/.muecore/mue.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.muecore/mue.conf
chmod 0600 ~/.muecore/mue.conf
mued -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"MUE\"}"

#--------------------- HUSH ----------------------

cd ~/wallets
git clone https://github.com/MyHush/hush
cd hush
./zcutil/build.sh --disable-tests -j4
sudo cp src/hushd src/hush-cli /usr/local/bin/
mkdir ~/.hush
echo "server=1" >> ~/.hush/hush.conf
echo "listen=0" >> ~/.hush/hush.conf
echo "listenonion=0" >> ~/.hush/hush.conf
echo "rpcuser=barterhush" >> ~/.hush/hush.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.hush/hush.conf
chmod 0600 ~/.hush/hush.conf
hushd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"HUSH\"}"

#--------------------- ARC ----------------------

cd ~/wallets
git clone https://github.com/ArcticCore/arcticcoin
cd arcticcoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.arcticcore
echo "server=1" >> ~/.arcticcore/arcticcoin.conf
echo "litemode=1" >> ~/.arcticcore/arcticcoin.conf
echo "listen=0" >> ~/.arcticcore/arcticcoin.conf
echo "listenonion=0" >> ~/.arcticcore/arcticcoin.conf
echo "rpcuser=barterarc" >> ~/.arcticcore/arcticcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.arcticcore/arcticcoin.conf
chmod 0600 ~/.arcticcore/arcticcoin.conf
arcticcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ARC\"}"

#--------------------- MONA ----------------------

cd ~/wallets
git clone https://github.com/monacoinproject/monacoin
cd monacoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.monacoin
echo "server=1" >> ~/.monacoin/monacoin.conf
echo "listen=0" >> ~/.monacoin/monacoin.conf
echo "listenonion=0" >> ~/.monacoin/monacoin.conf
echo "rpcuser=bartermona" >> ~/.monacoin/monacoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.monacoin/monacoin.conf
chmod 0600 ~/.monacoin/monacoin.conf
monacoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"MONA\"}"

#--------------------- LBC ----------------------

cd ~/wallets
git clone https://github.com/lbryio/lbrycrd
cd lbrycrd
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.lbrycrd
echo "server=1" >> ~/.lbrycrd/lbrycrd.conf
echo "listen=0" >> ~/.lbrycrd/lbrycrd.conf
echo "listenonion=0" >> ~/.lbrycrd/lbrycrd.conf
echo "rpcuser=uselbc" >> ~/.lbrycrd/lbrycrd.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.lbrycrd/lbrycrd.conf
chmod 0600 ~/.lbrycrd/lbrycrd.conf
lbrycrdd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"LBC\"}"

#--------------------- ARG ----------------------

cd ~/wallets
git clone https://github.com/argentumproject/argentum
cd argentum
./autogen.sh
CFLAGS="-O2 -fPIC -DUSE_SSE2" CPPFLAGS="-O2 -fPIC -DUSE_SSE2" ./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.argentum
echo "server=1" >> ~/.argentum/argentum.conf
echo "listen=0" >> ~/.argentum/argentum.conf
echo "rpcuser=barterarg" >> ~/.argentum/argentum.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.argentum/argentum.conf
chmod 0600 ~/.argentum/argentum.conf
argentumd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ARG\"}"

#--------------------- PIVX ----------------------

cd ~/wallets
git clone https://github.com/PIVX-Project/PIVX
cd PIVX
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.pivx
echo "server=1" >> ~/.pivx/pivx.conf
echo "litemode=1" >> ~/.pivx/pivx.conf
echo "listen=0" >> ~/.pivx/pivx.conf
echo "staking=0" >> ~/.pivx/pivx.conf
echo "rpcuser=barterpivx" >> ~/.pivx/pivx.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.pivx/pivx.conf
chmod 0600 ~/.pivx/pivx.conf
pivxd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"PIVX\"}"

#--------------------- VTC ----------------------

cd ~/wallets
git clone https://github.com/vertcoin/vertcoin
cd vertcoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.vertcoin
echo "server=1" >> ~/.vertcoin/vertcoin.conf
echo "listen=0" >> ~/.vertcoin/vertcoin.conf
echo "listenonion=0" >> ~/.vertcoin/vertcoin.conf
echo "rpcuser=bartervtc" >> ~/.vertcoin/vertcoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.vertcoin/vertcoin.conf
chmod 0600 ~/.vertcoin/vertcoin.conf
vertcoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"VTC\"}"

#--------------------- ZEC ----------------------

cd ~/wallets
git clone https://github.com/zcash/zcash
cd zcash
./zcutil/build.sh --disable-tests -j4
sudo cp src/zcashd src/zcash-cli src/zcash-tx /usr/local/bin/
mkdir ~/.zcash
echo "server=1" >> ~/.zcash/zcash.conf
echo "listen=0" >> ~/.zcash/zcash.conf
echo "listenonion=0" >> ~/.zcash/zcash.conf
echo "rpcuser=barterzec" >> ~/.zcash/zcash.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.zcash/zcash.conf
chmod 0600 ~/.zcash/zcash.conf
zcashd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"ZEC\"}"

#--------------------- VIA ----------------------

cd ~/wallets
git clone https://github.com/viacoin/viacoin
cd viacoin
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.viacoin
echo "server=1" >> ~/.viacoin/viacoin.conf
echo "listen=0" >> ~/.viacoin/viacoin.conf
echo "listenonion=0" >> ~/.viacoin/viacoin.conf
echo "rpcuser=bartervia" >> ~/.viacoin/viacoin.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.viacoin/viacoin.conf
chmod 0600 ~/.viacoin/viacoin.conf
viacoind -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"VIA\"}"

#--------------------- UIS ----------------------

cd ~/wallets
git clone https://github.com/unitusdev/unitus
cd unitus
./autogen.sh
./configure --with-incompatible-bdb --with-gui=no --disable-tests --disable-bench --without-miniupnpc
make -j4
sudo make install
mkdir ~/.unitus
echo "server=1" >> ~/.unitus/unitus.conf
echo "listen=0" >> ~/.unitus/unitus.conf
echo "listenonion=0" >> ~/.unitus/unitus.conf
echo "rpcuser=barteruis" >> ~/.unitus/unitus.conf
echo "rpcpassword=`head -c 32 /dev/urandom | base64`" >> ~/.unitus/unitus.conf
chmod 0600 ~/.unitus/unitus.conf
unitusd -daemon

curl --url "http://127.0.0.1:7779" --data "{\"userpass\":\"$userpass\",\"method\":\"enable\",\"coin\":\"UIS\"}"

