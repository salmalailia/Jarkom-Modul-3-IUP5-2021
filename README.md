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

![1 2](https://user-images.githubusercontent.com/73702347/140918555-2f19b29c-8c84-449c-8b45-d3346426ecf4.jpg)

![1 3](https://user-images.githubusercontent.com/73702347/140918587-41ca8377-08b8-4b34-b42a-b41ad8c332bc.jpg)

On Jipangu
Change configuration interface in isc-dhcp-server

![1 4](https://user-images.githubusercontent.com/73702347/140918592-f910d835-c272-4c83-913f-ee0c2660886e.jpg)

## no. 2

and Foosha as DHCP Relay (2)

### Answer

Add a script to install relay on foosha

![2 1](https://user-images.githubusercontent.com/73702347/140919132-19526c24-9269-47fd-98ef-acaba2c890e6.jpg)

then change the config on relay /etc/default/isc-dhcp-relay

![2 2](https://user-images.githubusercontent.com/73702347/140919142-13746365-5d5a-4856-a1a5-e530fef34533.jpg)

Server points to jipangu because it acts as a relay, and Interfaces to eth1 2 3 which is switch 1 2 3.

## no. 3

1. All existing clients MUST use the IP configuration from the DHCP Server

### Answer

Number 1, edit the network config Alabasta, Loguetown, Skypie, Tottoland to

There are several criteria that Luffy and Zoro want to make, namely:

1. All existing clients MUST use the IP configuration from the DHCP Server.
2. Clients passing through Switch1 get IP ranges from [IP prefix].1.20 - [IP prefix].1.99 and [IP prefix].1.150 - [IP prefix].1.169 (3)
3. Clients that go through Switch3 get IP ranges from [IP prefix].3.30 - [IP prefix].3.50 (4)
4. The client gets DNS from EniesLobby and the client can connect to the internet through the DNS. (5)
5. The length of time the DHCP server lends the IP address to the client via Switch1 is 6 minutes, while the client via Switch3 is 12 minutes. With a maximum time allocated for borrowing an IP address for 120 minutes. (6)

Number 2, add config in isc-dhcp-server (jipangu)

![3 1](https://user-images.githubusercontent.com/73702347/140919518-3357af0a-b3dc-4611-94d2-68009c73d709.jpg)

![3 2](https://user-images.githubusercontent.com/73702347/140919533-e82cb1d5-529c-492e-8518-f29678687b6a.jpg)

## no. 7

Luffy and Zoro plan to use Skypie as a server for buying and selling ships they own with a fixed IP address with IP [prefix IP].3.69 (7)

### Answer

First, take the hwaddress on Skypie

![7 1](https://user-images.githubusercontent.com/73702347/140920056-ed01d2d8-8220-4821-a502-8e9d6593b031.jpg)

Then config on Jipangu, dhcpd.conf

![7 2 5](https://user-images.githubusercontent.com/73702347/140920089-5ff818fe-2164-4d38-9a3e-8dd5ca6443ff.jpg)

Then add it to the skypie config

![7 2](https://user-images.githubusercontent.com/73702347/140920081-ccd29a44-f470-41e4-9e63-a682c9bd11e1.jpg)

![7 4](https://user-images.githubusercontent.com/73702347/140920098-8078b510-cd9c-4b58-9268-827a62355115.jpg)

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

