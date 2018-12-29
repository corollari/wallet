# TERA Smart money

* [Light client (zip)](https://github.com/terafoundation/wallet/raw/master/Bin/Light/Tera-light.zip)
* [Wallet handbook - PDF](https://drive.google.com/file/d/1ej-8jkjKd3p78vdGXWkzzVJq5PTgyxEw/view?usp=sharing)
* [<Документация на русском>](https://github.com/terafoundation/wallet/tree/master/Doc/Rus)


Attention:
* For a quick initial download of the wallet, there is a [link](https://github.com/terafoundation/wallet/raw/master/Torrent/Tera-folder-DB.torrent) to download the database via the P2P Protocol. Download the file via torrent and unzip it. Next, put the DB folder in the data directory of the wallet (with full replacement).
* After the installation shown below, enter the address your server in the browser. Example: 12.34.56.78:8080
* For mining You must have a static (public) IP address and an open port.
* We recommend not storing private keys on remote servers.
* We recommend putting an additional password on the private key ("Set password" button) - in this case the private key will be stored in file in encrypted form.
* If you do not set http-password, you can access only from the local address: 127.0.0.1:8080
* For remote access to the node only from the specified computer set the HTTP_IP_CONNECT constant (for example: "HTTP_IP_CONNECT": "122.22.33.11")


## Installing from setup on Windows:
https://github.com/terafoundation/wallet/raw/master/Bin/Win64/tera_setup.exe


## Installing from source code on Windows by steps:

1. Download and install Nodejs https://nodejs.org (v8.11 is recommended)
2. Download and install git https://git-scm.com/download/win
3. Then run the commands (in program: cmd or PowerShell):

```
cd ..\..\..\
git clone https://github.com/terafoundation/wallet.git
cd wallet/Source
npm install
node set httpport:8080 password:<secret word (no spaces)>
run-node.bat

```
If you want to run the wallet as a background process, then instead of the last command (run-node.bat), do the following:
```
npm install pm2 -g
pm2 start run-node.js
```

### Opening ports:
```
netsh advfirewall firewall add rule name="Open 30000 port" protocol=TCP localport=30000 action=allow dir=IN
```

### Updates

```
cd wallet
git reset --hard 
git clean -f
git pull 
```



## Installation on Linux 

### CentOS 7:


```
sudo yum install -y git
curl --silent --location https://rpm.nodesource.com/setup_8.x | sudo bash -
sudo yum  install -y nodejs
sudo npm install pm2 -g
sudo git clone https://github.com/terafoundation/wallet.git
cd wallet/Source
sudo npm install
sudo node set httpport:8080 password:<secret word (no spaces)>
sudo pm2 start run-node.js
```

### open ports (all):
```
systemctl stop firewalld 
systemctl disable firewalld
```

### Updates

```
cd wallet
sudo git reset --hard 
sudo git clean -f
sudo git pull 
```



### UBUNTU 18.4:

```
sudo apt-get install -y git
sudo apt-get install -y nodejs
sudo apt-get install -y npm
sudo npm install pm2 -g
sudo git clone https://github.com/terafoundation/wallet.git
cd wallet/Source
sudo npm install
sudo node set httpport:8080 password:<secret word (no spaces)>
sudo pm2 start run-node.js
```

### open ports:

```
sudo ufw allow 30000/tcp
sudo ufw allow 8080/tcp
```




### Updates

```
cd wallet
sudo git reset --hard 
sudo git pull 
```

## MAIN NETWORK
Default values:
```
port:30000
httpport:8080
```



## TEST NETWORK
Default values:
```
port:40000
httpport:8080
```
Launch: 
```
cp -a Source SourceTest
cd SourceTest
sudo node set-test httpport:8080 password:SecretWord
sudo pm2 start run-test.js
```








## Specification

* Name: TERA
* Consensus: PoW
* Algorithm:  Terahash (sha3 + Optimize RAM hashing)
* Total suplay: 1 Bln
* Reward for block: 1-20 coins, depends on miner power (one billionth of the remainder of undistributed amount of coins and multiplied by the hundredth part of the square of the logarithm of the miner power)
* Block size 120 KB
* Premine: 5%
* Development fund: 1% of the mining amount
* Block generation time: 1 second
* Block confirmation time: 8 seconds
* Speed: from 1000 transactions per second
* Commission: free of charge 
* Cryptography: sha3, secp256k1
* Protection against DDoS: PoW (hash calculation)
* Platform: Node.JS


# FAQs

## Mining is possible only on a public IP
* Check the presence of a direct ip-address (order from the provider)
* Check if the port is routed from the router to your computer
* Check the firewall (port must open on the computer)



## Refs:
* Web: http://terafoundation.org
* Btt: https://bitcointalk.org/index.php?topic=4573801.0
* Twitter: https://twitter.com/terafoundation
* Telegram: https://web.telegram.org/#/im?p=@terafoundation
* Discord: https://discord.gg/CvwrbeG
* [DEX-guide](https://docs.google.com/document/d/1qvVRfLq3qcYYF6dcsAAAqoGyBFF4njXUYZXZfTPWd2w/edit?usp=sharing)
* [BTC for DEX](https://docs.google.com/document/d/19vRY6tkbTP8tubZxM01llwnMyz4P6IzY0zvnargrU6k/edit?usp=sharing)
* [Эта же страница на русском](https://github.com/terafoundation/wallet/tree/master/Doc/Rus)
* [Torrent of blockchain - DATA/DB folder](https://github.com/terafoundation/wallet/raw/master/Torrent/Tera-folder-DB.torrent)
* [API](https://github.com/terafoundation/wallet/blob/master/Doc/Eng/API.md)



