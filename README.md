# Jarkom-Modul-3-IUP5-2021


Group IUP 5 :

Hilmy Hanif Ibrahim (05111942000005)

Salma Rahma Lailia  (05111942000016)

Khairi Wiryawan     (05111942000023)


# Module 3

## no. 1

Luffy and Zoro plan to make the map with the criteria of Enies Lobby as DNS Server, Jipangu as DHCP Server, Water7 as Proxy Server

### Answer

Enies → bind9

Jipangu → isc-dhcp-server

Water7 → squid

![1 1](https://user-images.githubusercontent.com/73702347/140918006-13b947c5-f4f2-44b3-b844-49d6d34cc785.jpg)

On Jipangu
Change configuration interface in isc-dhcp-server

## no. 2

and Foosha as DHCP Relay (2)
Add a script to install relay on foosha

then change the config on relay /etc/default/isc-dhcp-relay

Server points to jipangu because it acts as a relay, and Interfaces to eth1 2 3 which is switch 1 2 3.

## no. 3

1. All existing clients MUST use the IP configuration from the DHCP Server.

Number 1, edit the network config Alabasta, Loguetown, Skypie, Tottoland to

There are several criteria that Luffy and Zoro want to make, namely:

1. All existing clients MUST use the IP configuration from the DHCP Server.
2. Clients passing through Switch1 get IP ranges from [IP prefix].1.20 - [IP prefix].1.99 and [IP prefix].1.150 - [IP prefix].1.169 (3)
3. Clients that go through Switch3 get IP ranges from [IP prefix].3.30 - [IP prefix].3.50 (4)
4. The client gets DNS from EniesLobby and the client can connect to the internet through the DNS. (5)
5. The length of time the DHCP server lends the IP address to the client via Switch1 is 6 minutes, while the client via Switch3 is 12 minutes. With a maximum time allocated for borrowing an IP address for 120 minutes. (6)

Number 2, add config in isc-dhcp-server (jipangu)

## no. 7

Luffy and Zoro plan to use Skypie as a server for buying and selling ships they own with a fixed IP address with IP [prefix IP].3.69 (7)

First, take the hwaddress on Skypie

Then config on Jipangu, dhcpd.conf

Then add it to the skypie config

## no. 8

Loguetown is used as a Proxy client so that the safety of any transactions is secured and to prevent any transaction data leak. In Loguetown, proxy must be accessible under the name **jualbelikapal.yyy.com** with port 5000. (8)

In squid.conf on Water7, add

then turn on squid

**Testing**
For testing in Loguetown, we have to turn on forwarders in DNS EniesLobby, that is on named.conf.options

then restart bind9

In Loguetown, install lynx
then add

**Allow**
Add allow to make it accessible 

## no. 9

To create a safer transaction environment and set two different website user, a user authentication is placed in the proxy with encryption MD5 and two usernames, luffybelikapalyyy with password luffy_yyy and zorobelikapalyyy with password zoro_yyy (9)

At Water7, we can use htpasswd

then add its squid config

**Testing**

## no. 10

Transaction cannot be done every day, that is why internet access is limited to be accessible every Monday-Thursday from 07:00-13:00 and every Tuesday-Friday from 17:00-03:00 until tomorrow (Saturday, 03:00) (10)

/etc/squid/acl.conf

then add its squid config

**Testing**

