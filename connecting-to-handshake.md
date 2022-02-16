# Connecting to Handshake Sites
*Note: most of the information in this guide is derivative of namebase's guide on the same subject, which can be found [here](https://learn.namebase.io/starting-from-zero/how-to-access-handshake-sites#hsd-full-node). This simply contains some extra commentary from me (Ed) and my experience/recommendations on what you should use.*

The Handshake blockchain allows for websites to be accessed via a decentralized DNS network. However, since this network is not formally implemented into pretty much every centralized DNS server, you need to do a little bit of setup to connect to the handshake network.

There's a couple of different methods to connecting to the network ranging from using a proxy gateway to running an actual handshake node. These methods are described in the following sections.

## Method 1: Proxy Gateways
Proxy Gateways are essentially a middleman between you and the HNS network. You make a request to a website such as [http://welcome.nb/](http://welcome.nb/), and the proxy handles finding the domain within the HNS network and retrieving the correct ip address.

This method works the best if you just want to poke around in the HNS network and don't want to bother setting up custom DNS connections or an HNS node.

**Note that this method isn't the most secure and is vulnerable to Man-in-the-Middle-style attacks.** If the proxy itself becomes compromised, it's possible that end users are redirected to malicious sites instead of the actual desired webpage. I recommended that if you want to use websites that requires entering sensitive information such as logins, payment/bank info, etc. that you use anything within method 3 instead.

The proxies that I use the most are [hns.to](https://hns.to) and [hns.is](https://hns.is). If you are on mobile, you can download the [Puma browser app](https://www.pumabrowser.com). Note that this app is still a proxy gateway as it uses hns.to to connect you to HNS-based websites.

## Method 2: External DNS Servers
This method involves setting your device to connect to a centralized DNS server that can also resolve HNS domains. This method aligns closely with how current DNS is handled, which means it's relatively simple to set up. This also means it is vulnerable to the same kinds of attacks that normal DNS servers are vulnerable to. 

**Because of this, it's recommended that you treat this similarly to Method 1 security-wise (OK for general browsing, don't trust for entering login or payment info or other sensitive information).**

The DNS Servers that I mainly use are [hdns.io](https://www.hdns.io). They have a setup guide on their website, but if you already know how to configure DNS on your device, the servers are `103.196.38.38` and `103.196.38.39`.

If you're using Chrome as your browser, you can also use the [Bob Extension](https://chrome.google.com/webstore/detail/bob-extension/ogcmjchbmdichlfelhmceldndgmgpcem) which also acts as an HNS wallet. After creating a wallet, you can enable the HNS resolver (which uses hsnd.io) in the settings menu.

## Method 3: Running an HSD or HNSD node

The most secure method to resolving handshake domains is to run either a full node (HSD) or a lightweight verification node (HNSD). I recommend that you use this option exclusively unless you are unable to.

There's some 3rd party software that makes resolving names in this manner very straightforward. The first is [Fingertip](https://impervious.com/fingertip.html) which runs a lightweight HNSD node and works on all desktop operating systems (MacOS, Windows, and Linux-based distros). Setup is fairly straightforward, install the software and let auto-configuration do the rest after running fingertip. 

If you're on an iOS device, you can use the [Beacon web browser](https://impervious.com/beacon), which also runs a lightweight HNSD node.

If you want to run a lightweight HNSD node directly or want to run a full HSD node, you can do that as well. *TODO: figure out how to do this as I haven't managed to get it working myself just yet.*
