
# Symbol Node Migration Guide 
![](https://i.imgur.com/uFKUcxh.png)




> **Required Knowledge Level:** 
> A sufficient level of knowledge is required to complete all the steps in [this](https://hackmd.io/Z7ErI0IZQ5Wer1s5-6wjpw) guide prepared by the [CB](http://xym.farm) and run the Symbol Node successfully.

> The Source and Target VPS mentioned in this guide are using Centos 8 OS.

> I used zip and unzip to backup and use the backup on Source and Target VPS. You can find the download guide [here](https://globedrill.com/how-to-install-zip-on-centos-8-server/).

> You can always get help from us regarding this process. Read the entire guide before you start, [contact](https://discord.gg/xymcity) us if there is a step you do not understand.

### Greetings Pirates!

Sometimes you may need to migrate your Symbol node to another PC or VPS. You don't want to lose accounts harvesting on your node while doing this!

For example, I started to run Symbol Node on my home PC. After a while, I migrated my node to a VPS. Because the electricity and internet infrastructure at home cannot be stable and we may encounter node crashes.

### Preparing Target VPS 

First we have to make our preparations on the target VPS.

* All the steps outlined in [this](https://hackmd.io/Z7ErI0IZQ5Wer1s5-6wjpw) guide (before starting the Symbol Node) must be completed on the target VPS.
* Preparing custom.yml file
    * If you are using domain name, you can use it on the target VPS without changing the custom.yml file you use in the source VPS.
      * You need to point your DNS Record to the target VPS IP address. 
     * If you are using a static Ip address, you should update it with the destination VPS Ip address in the custom.yml file.




### Preparing Source VPS

We will stop our currently running source node and take a backup.



```
symbol-bootstrap stop
```
After the process is complete, zip the target folder with the command below:

```
zip -r target.zip target
```

With the above command, we have included the chain data and taken it into the backup. This will be our Source VPS backup to run the same in case of any mishap.

We will delete the chain data to reduce the size of the target folder that we will send to the target VPS.

```
symbol-bootstrap resetData
```
After the process is complete, zip the target folder with the command below:

```
zip -r targetRD.zip target
```

Yes, our backup that we will send to the target VPS is ready. We will use linux's scp protocol to transfer this backup.

```
scp targetRD.zip user@targetVPSipaddr:~/
```
Enter TargetVPS User Password. 
Output should be like below:

```
targetRD.zip              100%    5     0.4KB/s   00:00
```
Now let's unzip our backup:


```
unzip targetRD.zip
```
You can run your node with the following command.
(We have prepared the custom.yml file before.)

```
symbol-bootstrap start -p mainnet -a dual -c custom.yml --upgrade
```

You should make sure that the target VPS starts using the backup we copied. You can follow this from the outputs with the 'Reusing' heading.

Looks like below : 

```
2021-10-07T14:59:08.256Z info     Password has been provided
2021-10-07T14:59:08.654Z info     Upgrading configuration...
2021-10-07T14:59:08.694Z info     Generating config from preset 'mainnet'
2021-10-07T14:59:08.694Z info     Using assembly 'dual'
2021-10-07T14:59:08.694Z info     Using custom preset file 'custom.yml'
2021-10-07T14:59:08.754Z info     Reusing Main Account NDF6M62WIJCCPD33FDKIKHJ5HLEKLPFHQ66KGYY Public Ley 2A144FBF4034AAC6493ACC9F798AAE3A55F18A928025E10CA73BC5634D3A4B82 ...
2021-10-07T14:59:08.765Z info     Reusing Transport Account NCINTNOZIFRMQMJ2RRPM5VFREHAST4YQ654HQKA Public Ley 0DCDB93F686AFF1C0B10644AEA0334B4D96FF6D1D682CB121F88395964E64107 ...
2021-10-07T14:59:08.787Z info     Reusing Remote Account NADQ7YGYUEIOF4ET6NQ2SENHGVPFY3RTASFH6HQ Public Ley 6281CF4E744B3CCB3325828AA9A1942F1D8C8127F8E12A0312AF11CB18EE95F0 ...
2021-10-07T14:59:08.803Z info     Reusing VRF Account NAD7XEFYS2KULZ5KZYFW5CWAEOREIABGLTTVZMY Public Ley A39739DBBBEAFFEE59152CFDDE3D5155417587EDE42D77A59B2B734E625003EE ...
2021-10-07T14:59:08.812Z info     Deleting folder target/nodes/node/server-config
2021-10-07T14:59:08.816Z info     Deleting folder target/nodes/node/broker-config
2021-10-07T14:59:08.818Z info     Deleting folder target/nodes/node/seed
2021-10-07T14:59:08.820Z info     Deleting folder target/gateways/rest-gateway
2021-10-07T14:59:08.823Z info     Certificates for node node have been previously generated. Reusing...
2021-10-07T14:59:08.824Z info     Generating node server configuration
2021-10-07T14:59:08.977Z info     Generating broker broker configuration
2021-10-07T14:59:09.046Z info     Node node is not voting.
2021-10-07T14:59:09.063Z info     Upgrading genesis on upgrade!
2021-10-07T14:59:09.063Z info     Deleting folder target/nemesis/seed
2021-10-07T14:59:09.317Z info     Configuration generated.
2021-10-07T14:59:09.318Z info     Deleting folder /home/symbolnode/target/docker
2021-10-07T14:59:09.331Z info     User for docker resolved: 1000:1000
```

Now Node started working on the new VPS. After fully syncing the chain data, you will be able to see the delegates connected to your node.

Whola! 



---
**DONATION**

If you like my guide, you can send something to the address below to support me.

**XYM**

NCN3DI6F2ZOA2LEWWB5NO65A5VBF6E2BYY6IC2Y

![](https://i.imgur.com/e3P88WU.png)


You can also support me as a delegate to my node!


[http://node.symboltr.blog:3000](http://node.symboltr.blog:3000)






