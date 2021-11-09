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

On Jipangu
Change configuration interface in isc-dhcp-server

## no. 2

and Foosha as DHCP Relay (2)

### Answer

Add a script to install relay on foosha

then change the config on relay /etc/default/isc-dhcp-relay

Server points to jipangu because it acts as a relay, and Interfaces to eth1 2 3 which is switch 1 2 3.

## no. 3

1. All existing clients MUST use the IP configuration from the DHCP Server.

### Answer

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

### Answer

First, take the hwaddress on Skypie

Then config on Jipangu, dhcpd.conf

Then add it to the skypie config

