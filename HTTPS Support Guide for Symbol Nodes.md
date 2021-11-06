![](https://i.imgur.com/DySzVhs.png)


# HTTPS Support Guide For Symbol Nodes

>Requied Knowledge Level : You should be able to run SymbolNode.

>Please read entire guide before start. If you don't understand some steps please ask me.

>You must have a domain name for certification.

>Be sure your Symbolnode runing. 



### Greetings Pirates!

In this guide, I will explain to you how to launch https-portal from another docker-compose without modifying the symbol-bootstrap docker file . 


#### Folder Creation

With the codes below, create a folder named "https-portal" in the same directory (not in the target folder!) of your Symbolnode's Target folder, then enter it.

```
$ mkdir https-portal
$ cd https-portal
```

#### Create docker-compose file

```
vi docker-compose.yml
```
Paste the following content into the docker-compose.yml file as it is, then replace the "node.symboltr.blog" part with your own domain name and save.

```
version: '3'
services:
    https-portal:
        container_name: https-portal
        image: 'steveltn/https-portal:1'
        ports:
            - '80:80'
            - '3001:443'
        restart: 'on-failure:2'
        environment:
            DOMAINS: 'node.symboltr.blog -> http://rest-gateway:3000'
            STAGE: 'production' 
            #LISTEN_IPV6: 'true'
            WEBSOCKET: 'true'
        volumes:
            - 'https-portal-data:/var/lib/https-portal'

volumes:
    https-portal-data:

networks:
    default:
        external:
            name: 'docker_default'
```


#### Run the Https-Portal Container

Then start the https server setup with the following code: 

```
docker-compose up
```
It takes time to obtain the certificate at the first startup.
(give 5 minuite to complete certification)

Access https://your.domain.name:3001/node/info with your browser

![](https://i.imgur.com/lHX4a6Y.png)

If everything is working correctly, you have completed everything. Close the SSH season.

Congratulations.

#### Troubleshooting

If you cant reach your Https address check mentioned issues: 

* Your node must be running otherwise browser can't find your node
* Check  port 3001 is Open
* Be sure any App or Container using  port 80 (like Apache,httpd)


####  Donation

If you like my guide, you can support me by 

Donate 

**XYM** NCN3DI6F2ZOA2LEWWB5NO65A5VBF6E2BYY6IC2Y

Delegation

http://node.symboltr.blog:3000

Purchasing most affordable VPS Contabo with my Ref link:

<a href="https://www.anrdoezrs.net/click-100515681-15022370" target="_top">
<img src="https://www.lduhtrp.net/image-100515681-15022370" width="250" height="360" alt="" border="0"/></a>


You can Contact me by twitter
https://www.twitter.com/hexagon_tr


