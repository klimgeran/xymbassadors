###### tags: `guides` `resources`
# Ultimate Symbol Node Guide

[![hackmd-github-sync-badge](https://hackmd.io/Z7ErI0IZQ5Wer1s5-6wjpw/badge)](https://hackmd.io/Z7ErI0IZQ5Wer1s5-6wjpw)


## How to run a Symbol Node on CentOS 8 (for beginners)

#### From Zero to Hero.

Guide by [CB](http://xym.farm).

This time I will explain and show you step by step how to prepare and run a Symbol Node on a RS (root server) with CentOS 8. 

First thing you have to know is that you don't need to hold XYM to run a Symbol Node on your own or rented server.

### Other useful Symbol node guides:
<details>
  <summary>Details</summary>
* *Running a Symbol node official guide* https://docs.symbolplatform.com/guides/network/running-a-symbol-node.html
 
* *The 23 € Symbol Node by* Fernando Boucquez https://dev.to/fboucquez/the-23-symbol-node-3c41

* *How to setup a $40 Symbol Node on Allnodes* by Allnodes
(Min. 10k XYM required)
https://help.allnodes.com/en/articles/5119173-how-to-setup-a-symbol-harvester-node-or-supernode-on-allnodes

* *Symbol Node Resource Guide* by Sekoya Labs https://medium.com/@sekoyalabs/symbol-node-resource-guide-41237e10a07b

* *How to Run Symbol Node with Docker Desktop Windows 10* by Hexagon
https://community.nem.io/cboard/activity/38154-how-to-run-symbol-node-with-docker-desktop-windows-10/
</details>

---

Ok, so assuming you’ve decided to follow my guide, here we go:

First off, you need a server running CentOS 8. If you already have one, skip to "**Connecting to your server**".

Make sure to check the Hardware requirements before you rent a server.

### Minimum node specifications 
<details>
  <summary>Details</summary>

| Requirement | Peer node     | API node      |
| ----------- | ------------- | ------------- |
| CPU         | 2 cores       | 4 cores       |
| RAM         | 8GB           | 16GB          |
| Disk size   | 500 GB        | 750 GB        |
| Disk speed  | 1500 IOPS SSD | 1500 IOPS SSD |

</details>

---

### Recommended node specifications

<details>
  <summary>Details</summary>

| Requirement | Peer node     | API node      | Dual & Voting node |
| ----------- | ------------- | ------------- | ------------------ |
| CPU         | 4 cores       | 8 cores       | 8 cores            |
| RAM         | 16GB          | 32GB          | 32GB               |
| Disk size   | 500 GB        | 750 GB        | 750 GB             |
| Disk speed  | 1500 IOPS SSD | 1500 IOPS SSD | 1500 IOPS SSD      |

</details>

---

### A list of websites from where you can rent a root server based on your needs.
<details>
  <summary>Details</summary>
Only Netcup and Contabo servers have been tested so far.
It’s better and essential that we don’t rent our servers all from the same place and try to spread across the globe, so if you live in the USA, you could try to host a server in the USA or close by. Some websites might even require some time to process your information (KYC) before you are able to start with your node’s installation.
### https://www.netcup.eu/vserver/
AMD EPYC™ 7702 - RS 2000 G9 starting at €16 / month (stable – tested on mainnet and testnet)
- GER
- 16 GB DDR4 RAM (ECC)
- 4 dedicated cores
- 320 GB SSD

![](https://i.imgur.com/uKHKaSv.png)
--

#### https://contabo.com/en/vps 
VPS S SSD starting at €4,99 / month 
- GER, US (central), US (east), US (west), ASIA 
- CPU Cores: 4 
- 8 GB
- 200 GB SSD

![](https://i.imgur.com/QpXFA8n.png)
--

#### https://zap-hosting.com/en/shop/product/linux-rootserver/
Root linux server starting at €12,90 / month (I haven’t tested it yet - make your custom server based on your needs or requirements)
- GER, UK, FIN, USA, CA, BRA, AU, ASIA
- CPU Cores: 4
- 16GB DDR4 RAM
- 320 GB SSD

![](https://i.imgur.com/kpgNkjI.png)
 
---

#### https://www.strato.nl/server/dedicated-server-linux/
AMD Opteron 4180 - DEDICATED LINUX SERVER D200 starting at €31 / month
- NL
- 6 x 2,6 GHz
- 16 GB RAM
- 2 TB HDD

![](https://i.imgur.com/zfN7uRC.png)
</details>

---

*I suggest you follow the next steps after you have access to your server control panel. Usually you get a welcome email from your hosting.*

Some servers might come with a preinstalled OS, so you’ll have to go in your SCP (server control panel), media / images and install CentOS 8 

### How to install CentOS 8 from your server's control panel
<details>
  <summary>Details</summary>

![](https://i.imgur.com/rQKdZFY.png)

Access your SCP by going to https://www.servercontrolpanel.de
From here you go to Media / Images / Distribution → CentOS 8 (Minimal...)

![](https://i.imgur.com/TRxsYDQ.png)


Next click Minimal / minimal system with ssh preinstalled

![](https://i.imgur.com/UOEHlUG.png)

Now you have 2 options:
small partition layout for individual use
one big partition with Os as root partition. Installation may take longer to finish

I went for one big partition, because if you remember, you need at least 750 GB (peer 500 GB and api 750 GB) to run a dual node, based on the minimum requirements, but for the moment you can get it running without a problem with a 320GB HDD. 
Later we’ll have to upgrade to a much more powerful server or if your platform permits it, just modify your plan.

![](https://i.imgur.com/4VLpOhE.png)


If you proceed with this all the data on your server will be deleted and you will get a fresh copy of CentOS 8.

In the next step you’ll have to type in your SCP login password and click on reinstall.

**“If you start the reinstall, all data on the hard disk will be purged. The server will be reinstalled with the values displayed above.”**

![](https://i.imgur.com/lYtmLHM.png)

Server stopped
copy of image running

![](https://i.imgur.com/M97jFOs.png)

Starting server

![](https://i.imgur.com/h5nbNZk.png)

Installation running (you can close the window that popped-up)

![](https://i.imgur.com/zszYhLp.png)

If you’re wondering what is that pop-up, it’s exactly what’s happening on your server right now:
files and packages are being installed...

Installation running wait or do other things meanwhile

![](https://i.imgur.com/4inE0ss.png)

Installation finished. 

![](https://i.imgur.com/C5KyYU5.png)

Now that CentOS 8 is running on your server, you know your ip/hostname and root password, we can proceed to the next step. 

What’s the next step? 
Connecting to your server.


</details>

---

### Connecting to your server
<details>
  <summary>Details</summary>
You can connect to your server either by using your console “ssh root@YourIP” 

![](https://i.imgur.com/1WV0DOX.png)

or by using a small program called Putty. You can download it from putty.org 

I’m always using Putty because old habits die hard :)

![](https://i.imgur.com/VpAk8ez.png)

Write your server’s ip/hostname or copy/paste it in the “Host Name (or IP address)” field, and click Open.


```
Login as: root
root@YourIP’s password: Paste your password with right click
``` 

Copy / Paste (right click) the root password you got in your email or in the control panel window of your CentOS 8 installation.


After you’ve successfully logged in with your root username, your screen should look similar to this:

![](https://i.imgur.com/IRNhwOu.png)
</details>

---

#### For the next steps make sure you copy / paste each command, one at a time. 
**Make sure you don't type any extra characters or spaces. 
The smallest changes in code will result in error.**

### Creating a new user account
<details>
  <summary>Details</summary>

### Use following command to create the user account symbolnode:
`adduser symbolnode`

Set the password for the freshly created user account with the following command:

`passwd symbolnode`

[enter new password twice]

Add the user to the sudo-enabled usergroup (we need the sudo command for installation later) and switch to the symbolnode useraccount:

```
usermod -aG wheel symbolnode
su - symbolnode
```
</details>


### Install environment requirements
<details>
  <summary>Details</summary>

### Install and configure docker with the following commands:

`sudo yum install -y yum-utils`

```
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
```

`sudo yum install docker-ce docker-ce-cli containerd.io -y`

`sudo usermod -aG docker symbolnode`

`sudo systemctl start docker`

`sudo systemctl enable docker`

Install docker-compose with the following commands:

`sudo dnf install curl`

`sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`

`sudo chmod +x /usr/local/bin/docker-compose`

Install node.js with the following commands:

`sudo dnf module enable nodejs:12`

`sudo dnf install nodejs -y`

Install Nano with following command:

`sudo yum install nano`

**Reboot your server and login with the symbolnode user account we have created earlier.**

Verify environment requirements
To verify that the environment installations were successful, we can run following commands:

For docker, run:

`sudo docker run hello-world`

The output should be similar to:

*Hello from Docker!
This message shows that your installation appears to be working correctly.
[...]
For more examples and ideas, visit:
 https://docs.docker.com/get-started/*

For docker-compose, run:

`docker-compose version`

The output should be similar to:

*docker-compose version 1.28.5, build c4eb3a1f
docker-py version: 4.4.4
CPython version: 3.7.10
OpenSSL version: OpenSSL 1.1.0l  10 Sep 2019*

For node.js, run:

`node --version`

The output should be similar to:

*V12.21.0*


 Once you have verified your docker-compose version and node version, you can continue with the installation of symbol-bootstrap.
</details>

### Install and configure symbol-bootstrap
<details>
  <summary>Details</summary>


### Use the following command to install symbol-bootstrap:

`sudo npm install -g symbol-bootstrap`


Before we will run it, we will create a custom configuration file *custom.yml* with *Nano*.
In this file we need to add the following:\

*maxUnlockedAccounts* - is the maximum number of users allowed to harvest on your node
*friendlyName* - is the name of your node
*host* -  is the IP address of your node (can also be a domain name that you link to your server's ip)
*BeneficiaryAddress* - is the Symbol Account which will get the node operator fee.
*minFeeMultiplier* - is the minimum fee multiplier accepted by the node being queried

Run the following command to create and open your *custom.yml*: 

`nano custom.yml`

Paste your config, for example:
```
maxUnlockedAccounts: 100

nodes:
    - friendlyName: 'Name Of Your Node'
      host: IP or Hostname
      beneficiaryAddress: YourSymbolAddress
      minFeeMultiplier: 10
```

When you are done editing press *CTRL + O* to write the new changes to your custm.yml file and press *ENTER*.
*CTRL + X* to quit file.


Since 31 Mar 2021 TransactionSelectionStrategy's new default value is oldest so we don’t need to add it in the custom.yml
For more configuration properties, check Configuring node properties — Symbol Documentation 16

Now we are finally ready to run symbol-bootstrap with custom.yml for the first time!

To do so, use the following command:

`symbol-bootstrap start -p mainnet -a dual -c custom.yml`

[enter password]

***Enter a strong password, this password will be used to encypt files on your node, including the private keys of the node accounts
Let it run for 2-3 minutes, then stop it by pressing ctrl + c.
Before we run it again, we want to save our node accounts (including private keys).***

To do so, decrypt the addresses.yml file with the following command:

`symbol-bootstrap decrypt  --source target/addresses.yml --destination plain-addresses.yml`

[enter the password you have just used to encrypt the files]

This will create a new file plain-addresses.yml which is readable.
Open the plain-addresses.yml with following command:

`nano plain-addresses.yml`

Write down the privatekeys of every account, you can use them to restore the accounts in case you have to.
After you have all information written down, close it by pressing *CTRL + X*.

We are going to remove this file from the server with following command:

`rm plain-addresses.yml`

Running the node
After installation and configuration you are ready to run your node
Use following command:

`symbol-bootstrap start -p mainnet -a dual -c custom.yml -d`

[enter the password you have used to encrypt the files]

-p mainnet states that we are using the mainnet
-a dual states that we are running a dual (peer and API) node
-c custom states that we are using a custom configuration file
-d detached mode, symbol bootstrap will run in the background.

To check if your symbol-bootstrap was installed correctly run:

`symbol-bootstrap verify`

To get a full list of different presets, check [Using Symbol Bootstrap — Symbol Documentation](https://docs.symbolplatform.com/guides/network/using-symbol-bootstrap.html)
Validate the setup

Connect to your node via web, check that the following URLs return valid data.

http://YourNodesIP:3000/node/info for node health.

http://YourNodesIP:3000/chain/info for node connection to the mainnet.
</details>


### Updating symbol-bootstrap
<details>
  <summary>Details</summary>

**You don't need to update your symbol-bootstrap if you've just installed it.**

### To update the version of symbol-bootstrap, use following commands:

`symbol-bootstrap stop`

`cp -r target target_backup`

`sudo npm install -g symbol-bootstrap`

`symbol-bootstrap start -p mainnet -a dual -c custom.yml --upgrade -d`

Check the version by running:

`symbol-bootstrap --help`

If update was successful, remove backup of target folder:

`rm -r target_backup`

</details>

---

### Useful commands

<details>
  <summary>Details</summary>

To stop your node use:

`symbol-bootstrap stop`

To check if symbol-bootstrap runs without problems use:

`symbol-bootstrap healthCheck`

To update your config, use:
(it’s recommended to backup the target folder before you do this)
(edit your custom.yml config file)

```
symbol-bootstrap stop
symbol-bootstrap start -p mainnet -a dual -c custom.yml --upgrade  -d
```

To start fresh with symbol-bootstrap, for example if you experience problems with the config, use following commands:

`symbol-bootstrap stop`

`docker system prune -a`

`sudo rm -r target`
</details>

---

### How to link your node's IP to a hostname / domain name

<details>
  <summary>Details</summary>

First you need a domain. If you don't have one, get one.

1. Create a subdomain like node.YourDomain.com from your domain's hosting website.
 
Example: node.YourDomain.com

2. Redirect it to http://YourNodeIP 

Example: http://202.101.250.1

![](https://i.imgur.com/sBsuk9o.png)

3. From your DNS Zone Editor, edit your subdomain's ip to YourNode'sIP (without http)

![](https://i.imgur.com/uIub2Si.png)

4. Check if the redirect works. It might take from a few minutes to a few hours.

Example: node.YourDomain.com:3000/node/health 

If you see something like this, it means the redirect has been done and working.

![](https://i.imgur.com/p9UlG9d.png)

5. Go to your Customer Control Panel in your server's host. In my case it's https://www.customercontrolpanel.de

6. Change your rDNS to your newly created subdomain for your node

Example: node.YourDomain.com

![](https://i.imgur.com/hMFrHiS.png)

7. Login to your server using symbolnode username

8. Write `nano custom.yml` to edit your custom.yml file. If you are done press CTRL + O to save, ENTER, and CTRL + X to quit file.

![](https://i.imgur.com/O2mYa0D.png)

9. Change host from YourIP to YourDomain

![](https://i.imgur.com/fbO0Sev.png)

10. Once you are done editing your custom.yml file, press ESC and write `:wq`

11. Now you'll have to restart your symbol-bootstrap

To do this copy / paste the following commands one at a time.

`symbol-bootstrap stop`

Wait for bootstrap to stop

`symbol-bootstrap start -p mainnet -a dual -c custom.yml --upgrade  -d`

Wait for bootstrap to start

To check if symbol-bootstrap runs without problems use:

`symbol-bootstrap healthCheck`

![](https://i.imgur.com/puPZTeA.png)

12. Go to [Symbol Explorer](http://explorer.symbolblockchain.io/nodes)  and look for your node. 

![](https://i.imgur.com/56zTlfv.png)

It might take a few minutes for the changes to take place so don't get impatient if you don't see it right away.
</details>

---

### How to promote your Symbol node
<details>
  <summary>Details</summary>

1. Create a social media page dedicated to your node or use your own social media accounts to promote it.


2. Add your node's link in your bio and say something like: "Delegate to my node: ip/hostname:3000"

3. Make a dedicated and simple website for your node.

4. Talk about harvesting and share your node's hostname/ip with your followers, friends and other community members.

Example: http://xym.farm
</details>


### How to get your node listed on https://symbol-tools.com/symbolTools/view/tool/nodeList.html
<details>
  <summary>Details</summary>
![](https://i.imgur.com/1XX8oGq.png)

1. Send a minimum transaction of 10XYM to NBQTX4-XC7U3C-ZEVJU3-32KMFU-HO4KSR-N665FS-B2A including a message like the one you will see below.

**The transaction must be sent from the node's main symbol address, not from the beneficiary address.**

*If you already have access to your node's main address keep following the guide, otherwise skip to the next step and come back when you have access to your main node's address.*

#### To: NBQTX4-XC7U3C-ZEVJU3-32KMFU-HO4KSR-N665FS-B2A
#### Mosaic (1/1): 10 (XYM)
#### Message: {"limitHarvesterCount": "Number of max harvesters", "twitterAccount": "YourTwitterAccount", "comment": "Description of your node or any information you want to share with your potential future harvesters", "detailUrl": "YourNodeHostname"}

* limitHarvesterCount - max harvesters 
* twitteraccount without @ 
* comment: your node's description
* detailUrl: your node's host

2. To get on top of the list as you can see in the picture below, send a transaction from the **node's main symbol account** to the same address. 

NBQTX4-XC7U3C-ZEVJU3-32KMFU-HO4KSR-N665FS-B2A

Every XYM you donate to the developers of this tool gets you higher in "rank".

![](https://i.imgur.com/fZ0vAxb.png)

Here you can see the ranking for people who donated XYM: 

"XYM donations list for the last two weeks" 

https://symbol-tools.com/symbolTools/view/tool/donateAdGuide.html
![](https://i.imgur.com/4iLPy5l.png)

If want to have your node on top of the list, you'll have to donate more than the one who's on the spot you wish to be on.
</details>

---

### How to get your node's main address private key and add it in your Symbol Wallet

<details>
  <summary>Details</summary>

In order to send a transaction from your node's main symbol address, you need the private key. 
If you don't have it, you can get it by connecting to your server with your symbolnode username and by using the following commands:

`cd target` - accessing target folder

`symbol-bootstrap decrypt --source addresses.yml --destination decrypt.yml` - decrypting adresses.yml

[Enter password]

`nano decrypt.yml` - accessing decrypt.yml file

Copy your the private key for your main node's address and press *CTRL + X* to quit file.

`rm decrypt.yml` - removing decrypt.yml 

`exit` - exit console

Now you need to import your private key in your Symbol Wallet so you can send the needed transaction.

1. Login in your Symbol Wallet using your Symbol profile
2. Go to Accounts
3. Press " + Add an account"

![](https://i.imgur.com/y8OlPaB.png)

5. Select the type of account: I want to import an existing account private key

![](https://i.imgur.com/jYjEDIN.png)


7. Name your account, enter private key and your symbol wallet password and click "Confirm".

Your node's main account will show under "Private key accounts".

After adding your node's main address in your Symbol Wallet, go back to the last step and continue the guide on "How to get your node listed on https://symbol-tools.com/symbolTools/view/tool/nodeList.html"

</details>

---

### How to monitor your node on Telegram with [@XymHarvestMonitorbot](https://t.me/XymHarvestMonitorbot) 

<details>
  <summary>Details</summary>

This bot will help you monitor your node and wallet.

You will get notified every time:

* Your node's health check has failed / was succesful

![](https://i.imgur.com/ZcODuPh.png)

* One of your delegated harvesters has harvested a block on your node

![](https://i.imgur.com/OiGiR7e.png)

* You received a new transaction

![](https://i.imgur.com/g2zFf9C.png)

* You gain or lose a harvester

![](https://i.imgur.com/bHktD3l.png)


DM [@XymHarvestingMonitorbot](https://t.me/XymHarvestMonitorbot) and click START.

Next type `/language` and Click on `/language 0 英語`. 

Your language has changed from Japanese to English.

![](https://i.imgur.com/fNfUvPz.png)
英語 = English in Japanese

### Node commands:

`/addnode` domain name - Add one of your nodes

`/nodestatus` - Check node status

`/removenode` - Remove one of your nodes

### Wallet commands:

`/add` address name - Add one of your wallets

`/update` :address :newname - Change the name of a wallet

`/remove` :address - Remove one of your wallets

`/addresses` - List the addresses of all wallets grouped by the users

`/balance` - List the balances of all wallets

`/harvest` - List the harvestcount & totalfee of all wallets

`/setserver` - Set Delegated ServerName

### Other commands:

`/language` - 表示言語を変更します。

`/notify` - Change notification mode

`/txnotify` - Change transaction notification mode

`/tweet` - Change tweet link mode

</details>

---
