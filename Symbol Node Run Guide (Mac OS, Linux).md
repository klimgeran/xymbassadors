**Symbol Node Run Guide (Mac OS, Linux)**

Guide prepared by [@klimgeran](https://twitter.com/GeranKlim)

_____
Be sure to check out another guide that is more suitable for Windows users. Guide author[CB](http://xym.farm/):

More details 👉 [HERE](https://github.com/symbol/xymbassadors/blob/main/Ultimate_Symbol_Node_Guide.md) 
______

This manual will guide you through the process of setting up and connecting to the public SYMBOL network.

Nodes can function with different sets of components depending on your needs. The SYMBOL mainnet nodes are currently distributed in several forms:

1) Peer node
2) API node
3) Dual node and voting node

Minimum Requirements:

| Requirement|Peer node | API node  |Dual&Vot node|
| --------   | --------| -------- |-------- |
| CPU| 2 cores    | 4 cores     |4 cores |
| RAM| 8GB    | 16 GB     |16GB     |
| Disk size | 500 GB    | 750 GB     |750 GB     |
| Disk speed| 1500 IOPS SSD    | 1500 IOPS SSD  |1500 IOPS SSD|

https://docs.symbolplatform.com/guides/network/running-a-symbol-node.html

**To run our Symbol node, we can use Beget virtual hosting:**

![Beget](https://i.imgur.com/qdgmecq.png)

Next, choose the minimum “Strong” tariff plan, or you can choose the "Powerful" tariff, although the “Strong” tariff plan should be enough for you.

Make the following settings as shown below:
![Beget2](https://i.imgur.com/BURn9eB.png)

*  Build: “Strong”
*  OS: Centos 8
* Additional software: LAMP
* Create username and hosting name
* Create a password

You can choose other root vps for example: https://www.netcup.eu/vserver.

First, select the root server, confirm the data, go through the registration process, wait for a letter from netcup, verify your personal data.

We get a new password from https://www.servercontrolpanel.de/

We go to your personal account and open the section:
![1](https://i.imgur.com/Mx2isHY.png)
Next, move on to installing # centos 8 (core) - minimal
![2](https://i.imgur.com/lAwelUV.png)
![3](https://i.imgur.com/fcSOQJp.png)
Save your new root password and system data![4](https://i.imgur.com/j074kaL.png)

Preliminary steps for setting up hosting were shown here. Each hosting has its own settings, but this article showed the basic principle of how to properly set up your hosting. So that you can run your Symbol node on your hosting!

**Run the Symbol node via the terminal**

You need to follow this tutorial to get your Symbol node up and running.

Working in the terminal is pretty simple:

Open the terminal: **ssh root@44.132.44.88** 

**ssh root@(Your hosting ip)**

Root password, you should have received your password to your email: yvQy&^wd56 (Example)

**Use the following command to create a symbolnode user account:**

`adduser symbolnode`

**Set a password for your user account (Symbol node) using the following command:**

```
passwd symbolnode
```
`[enter new password twice]`

Add the user to the sudo-enabled user group (we'll need the sudo command to install later) and switch to the symbolnode user account:

```
usermod -aG wheel symbolnode
```
```
su - symbolnode
```

**Set environment requirements**
Install and configure docker with the following commands:

(Copy all these commands at once and paste into terminal)

```
sudo yum install -y yum-utils
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io -y
sudo usermod -aG docker symbolnode
sudo systemctl start docker
sudo systemctl enable docker
```

**Install docker-compose using the following commands:**

(Copy all these commands at once and paste into terminal)

```
sudo yum install -y yum-utils
sudo yum-config-manager \
    --add-repo \
    https://download.docker.com/linux/centos/docker-ce.repo
sudo yum install docker-ce docker-ce-cli containerd.io -y
sudo usermod -aG docker symbolnode
sudo systemctl start docker
sudo systemctl enable docker
```

**Install docker-compose using the following commands:**

(Copy all these commands at once and paste into terminal)

```
sudo dnf install curl
sudo curl -L "https://github.com/docker/compose/releases/download/1.28.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
```

**Install node.js using the following commands:**

`sudo dnf module list nodejs`
```
sudo dnf install nodejs -y
```

**Install VIM with the following command:**

```
sudo yum install vim-enhanced -y
```

(To test the work of docker, since docker is a platform for developing, delivering and running containerized applications) Enter the command: 

```
docker run hello-world
```

You should see the following message in the terminal:

![5](https://i.imgur.com/z10AGtp.png)

After that, we need to restart the Symbol node server and log in with the symbolnode account we created earlier.

**Use this command to reboot the server:**

```
sudo reboot
```

Then again, after restarting the server, open the command line (terminal) and go to your Symbol node:

**ssh symbolnode@’your_ip’**  
(Example: ssh symbolnode@45.141.78.132)
 
Enter the password you created earlier. You can copy the password using Command + C and paste into the command line (terminal) using Command + V.

**Verify environment requirements**

To verify that the installation of the environment was successful, we can run the following commands:

**For docker, run:**

```
docker run hello-world
```

The result should be similar to:
Hello from Docker!
This message shows that your installation appears to be working correctly.
[...]
For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 
**For docker-compose, run (Use the command)**:

```
docker-compose version
```

The result should be similar to the example below:

docker-compose version 1.28.5, build c4eb3a1f
docker-py version: 4.4.4
CPython version: 3.7.10
OpenSSL version: OpenSSL 1.1.0l  10 Sep 2019

To check the version of node.js run the command:

```
node --version
```

The result should be similar to the example below:

v10.24.0

Once you've verified the installation, you can proceed with the installation of symbol-bootstrap.

**Install and configure symbol-bootstrap**

Use the following command to install symbol-bootstrap:

```
sudo npm install -g symbol-bootstrap
```

You should see the following in the terminal:

![7](https://i.imgur.com/cg5Jfcl.png)

Before we will run node Symbol, we will create a custom configuration file custom.yml with VIM.

To do this, run the command:

```
nano custom.yml
```

**The custom file should look like this:**

```
nodes:
    - friendlyName: 'NameOfYourNode'
      host: IP
      beneficiaryAddress: YourNEMAccount
```


For example:
 
 
```
maxUnlockedAccounts: 100
 
nodes:
    - friendlyName: ’SymbolNodeTest’
      host: 45.141.78.132
      beneficiaryAddress: NFAX7GXDQA7IZRDEVVVZMDJGY5OLWNJVK7AFVUI
      minFeeMultiplier: 10
      transactionSelectionStrategy: oldest
```

![8](https://i.imgur.com/QGbVZ4j.png)

When you're done editing, press CTRL + O to commit the new changes to your custm.yml file and press ENTER. CTRL + X to exit the file.
 
Or perhaps:
 
Press ESC, then write the command: wq
 
 
Note:
 
(edit your custom.yml config file) 
symbol-bootstrap stop
vim custom.yml (Open file)
Select you want to overwrite: R
i (modify file)

Next, we can start the node:

```
symbol-bootstrap start -p mainnet -a dual -c custom.yml
```

```
Create a password
```

![9](https://i.imgur.com/9Xmbkjs.png)

We need to wait 1 minute and the node will start, then we stop our node using the command in the terminal ctrl + c

![10](https://i.imgur.com/NFLcIRx.png)

**After the Symbol node has stopped, write the command:**
 
`symbol-bootstrap decrypt --source target/addresses.yml --destination plain-addresses.yml`

![11](https://i.imgur.com/2PcNMPS.png)

**We enter this command**

```
vim plain-addresses.yml
```

(Save all data, addresses, private, public keys)

**Then enter the command to exit**

```
:q
```
**Enter another command (to remove custom.yml)**

```
symbol-bootstrap start -p mainnet -a dual -c custom.yml -d
```

**Checking the system**

```
symbol-bootstrap healthCheck
```

![12](https://i.imgur.com/CyPOpz3.png)

Run a node:
`symbol-bootstrap start -p mainnet -a dual -c custom.yml`
 
Сhecking the node in the browser:
`http://yourip:3000/node/info`

_________________________

**Obtaining the private key of the main address of your Symbol node and adding the private key to your Symbol Wallet**

To send a transaction from the address of the main Symbol node, you need a private key. If you don't have it, you can get it by connecting to your server with your username symbolnode and using the following commands:

We need to write this command in the terminal:

`symbol-bootstrap decrypt --source target/addresses.yml --destination plain-addresses.yml`

Next, enter the following command:
*vim plain-addresses.yml*

Now you need to import your private key into your Symbol wallet so that you can log into your Symbol node account through the Symbol Wallet.
1) Sign in to your Symbol wallet using your Symbol profile.
2) Go to accounts
3) Click "+ Add Account"

![](https://i.imgur.com/JXCmJwi.png)

4)  Select the type of account: I want to import the private key

![](https://i.imgur.com/rxkip3L.png)

5) Come up with a name for your account, enter the private key and password for your Symbol wallet and click "Confirm".

Your node main account will be displayed in the Accounts section.

# **Update custom.yml file:**

**Stop node to update settings** 

(edit your custom.yml config file) 
symbol-bootstrap stop
vim custom.yml (Open file)
Select you want to overwrite: R
i (change file)

We need to update the node:
```
symbol-bootstrap start -p mainnet -a dual -c custom.yml --upgrade -d
```

Checking the node:

```
symbol-bootstrap healthCheck
```
And run the node:

```
symbol-bootstrap start -p mainnet -a dual -c custom.yml
```

# Use the following commands to update the symbol-bootstrap node on Centos8:

1) `symbol-bootstrap stop` 
 
2) `cp -r target targetbackup`
 
3) `sudo npm install -g symbol-bootstrap`
 
4) `symbol-bootstrap start -p mainnet -a dual -c custom.yml --upgrade -d`
 
5) Version check:
`symbol-bootstrap --help`
 
6) If the update was successful, delete the backup using the command:
`rm -r targetbackup`


_________


































