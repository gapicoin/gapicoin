# Wellcome to gapicoin

It is the most popular and original gapicoin python script. The code is exceptionally portable and has been used successfully on a very broad range of ubuntu systems and hardware.

## Contact

[![Gitter](https://img.shields.io/gitter/room/nwjs/nw.js.svg)](https://gitter.im/gapicoin-github/)
[![GitHub Issues](https://img.shields.io/badge/open%20issues-0-yellow.svg)](https://github.com/omgbbqhaxx/gapicoin/issues)

- Chat in [gapicoin-github channel on Gitter](https://gitter.im/gapicoin-github).
- Report bugs, issues or feature requests using [GitHub issues](issues/new).



## Getting Started

The gapicoin Documentation site hosts the **[gapicoin homepage](http://gapicoin.com/)**, which
has a Quick Start section.

Operating system | Status
---------------- | ----------
Ubuntu and macOS | [![TravisCI](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://travis-ci.org/gapicoin/gapicoin-github)
Windows          | [![AppVeyor](https://img.shields.io/badge/build-passing-brightgreen.svg)](https://ci.appveyor.com/project/gapicoin/gapicoin-github)


```shell
sudo apt-get update -y && sudo apt-get upgrade -y && sudo apt-get install vim -y && sudo apt-get install python-dev -y && sudo apt-get install libevent-dev -y &&  sudo apt-get install python-virtualenv -y && apt-get install git -y

```



## Install python last version..

```shell
export LC_ALL="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt-get update
sudo apt-get install python3.4
sudo apt-get install python3-pip
apt install python-pip
sudo apt-get install libzmq3-dev libevent-dev python-dev python-virtualenv
pip install --upgrade virtualenv
virtualenv -p python3 venv

```

## Other configurations..

```shell
cd /opt/venv/

. bin/activate

git clone https://github.com/gapicoin/gapicoin.git

cd gapicoin

pip install -r requirements.txt

pipenv install requests
```


## After clone our project.

```shell
export DJANGO_SETTINGS_MODULE=gapicoin.settings
```

## Gunicorn configurations
The simplest way to install it is to use pip, a tool for installing and managing Python packages:
```shell
cd /opt/venv/bin
wget https://raw.githubusercontent.com/gapicoin/gapicoin/master/gunicorn_start
chmod u+x gunicorn_start
. gunicorn_start
```


## Circus: A Process & Socket Manager configurations
The simplest way to install it is to use pip, a tool for installing and managing Python packages:
```shell
pip install circus
pip install circus-web
pip install chaussette
```

example.ini
```shell
[watcher:startserver]
cmd = /opt/venv/bin/gunicorn_start
numprocesses = 1
[watcher:starttcpconnections]
cmd = python /opt/venv/gapicoin/p2p.py --host 18.222.186.94
numprocesses = 1
```

The file is then passed to circusd:
```shell
circusd example.ini
```

To always interact, service stays on continuously circusd:
```shell
circusd --daemon example.ini
```


You can exist from program if already running.
```shell
circusctl quit --waiting
```

## Finally we can complate nginx configuration!
NEWER FORGET TO CHANGE SERVER_NAME WITH YOUR IP ADDRESS FROM NGİNXCONF.!
```shell
sudo apt-get install nginx
sudo service nginx start
cd /etc/nginx/sites-available
wget https://raw.githubusercontent.com/gapicoin/gapicoin/master/nginxconf
ln -s /etc/nginx/sites-available/nginxconf /etc/nginx/sites-enabled/nginxconf
cd /opt/venv/
mkdir logs && cd logs
touch nginx-access.log && touch nginx-error.log
```


# REST APIs

## GET Endpoints
 * `http://gapicoin.com/api/v1/createnewwallet/` - allows to create new wallet and private key.

 * `http://gapicoin.com/api/v1/alltransactions/` - allows to get all transactions from database.

 * `http://gapicoin.com/api/v1/gettransaction/$transactionID` - allows to get transaction details.

 * `http://gapicoin.com/api/v1/getwalletfrompkey/$publicKey` - allows to create new wallet and private key.

 * `http://gapicoin.com/api/v1/getpublickeyfromprikey/$privateKEY` - allows to get public key from private key.

 * `http://gapicoin.com/api/v1/getbalance/$wallet` - allows to get last balance from wallet.

 *  `http://gapicoin.com/api/v1/getwalletdetails/$wallet` - allows to get all wallet history.





## POST Endpoints
  * `http://gapicoin.com/api/v1/sendgapicoin/`
  * `sprikey` sender's private key
  * `receiverwallet`  receiver's wallet
  * `amount`  and amount.
  ___


## Donations
  * Project gapicoin Wallet : `GAPIacb90db2827f18c5d4ef1476bd2498`

## License

[![License](https://img.shields.io/github/license/ethereum/cpp-ethereum.svg)](LICENSE)

All contributions are made under the [GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0.en.html). See [LICENSE](LICENSE).
