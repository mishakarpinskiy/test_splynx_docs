OpenVPN
====

![icon](icon.png)

If OpenVPN server isn't configured yet page will looks like:

![step1](step1.png)

By click on "Generate certificates" OpenVPN server certificates will be generated and you will be able use it.

![generate](generate_certs.png)

After specifying needed parameters here click on "Generate" and wait:

![generate done](generate_done.png)

Now OpenVPN server have to be configured and enabled:

![ready for config](ready_for_config.png)


![configuration](config.png)

Here can be configured port, mode(TCP or UDP), network, cipher, auth(hash function SHA1 or MD5) and authentication method.

Once server is configured, let's add some client.

![add client](add_client.png)

Specify connection name, IP and routes if needed. By click on "?" near router will be visible list with syntax of routes:

![routes guide](routes_guide.png)

Once client connection is created let's download credentials:

![download zip](client.png)

By this action "zip" archive will be downloaded with next files:

![downloaded files](downloaded_files.png)

I'm going to create VPN connection between Splynx(with OpenVPN server) and some desktop Ubuntu.

Let's add VPN connection in Ubuntu:

![add vpn](add_vpn.png)

Here specify gateway(IP of server), type and certificates + keys what are required. User key password in this setup can be missed. Next step is click on "Advanced":

![advanced1](advanced1.png)

Here we specified TCP connection(regarding to server configuration).

![advanced2](advanced2.png)

And here we have to specify Cipher(regarding server configuration).

Once it's done let's enable VPN connection and test:

![ifconfig](ifconfig.png)

Interface with given IP was created.

![ping](ping.png)

And network what was specified in routes(when we configured client) is accessible.

In Splynx status of connection changed to "Connected":

![connected](connected.png)

And by click on "Status" you can see some details about active connections:

![status](status.png)

By click on "Log" logs of VPN server can be checked.
