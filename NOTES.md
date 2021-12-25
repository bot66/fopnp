
### Special IP Addresses

(**local machine**)
* 127.\*.\*.\*: IP addresses that begin with the byte 127 are in a special, reserved range that is 
local to the machine on which an application is running. When your web browser or FTP 
client or Python program connects to an address in this range, it is asking to speak to some 
other service or program that is running on the same machine. Most machines make use of 
only one address in this entire range: the IP address 127.0.0.1 is used universally to mean 
“this machine itself that this program is running on” and can often be accessed through the 
hostname localhost.

(**local area network**)
* 10.\*.\*.\*, 172.16–31.\*.\*, 192.168.\*.\*: These IP ranges are reserved for what are called 
private subnets. The authorities who run the Internet have made an absolute promise: they 
will never hand out IP addresses in any of these three ranges to real companies setting up 
servers or services. Out on the Internet at large, therefore, these addresses are guaranteed 
to have no meaning; they name no host to which you could want to connect. Therefore, 
these addresses are free for you to use on any of your organization’s internal networks where 
you want to be free to assign IP addresses internally, without choosing to make those hosts 
accessible from other places on the Internet

### Routing 

* If the IP address looks like 127.\*.\*.\*, then the operating system knows that the packet is 
destined for another application running on the same machine. It will not even be submitted 
to a physical network device for transmission but handed directly to another application via 
an internal data copy by the operating system.
* If the IP address is in the same subnet as the machine itself, then the destination host can be found by simply checking the local Ethernet segment, wireless channel, or whatever the local 
network happens to be, and sending the packet to a locally connected machine.

* Otherwise, your machine forwards the packet to a gateway machine that connects your local 
subnet to the rest of the Internet. It will then be up to the gateway machine to decide where to 
send the packet after that

### Ports
When making decisions about defining port numbers, such as 53 for DNS, IANA thinks of them as falling into 
three ranges—and this applies to both UDP and TCP port numbers.

* Well-known ports (0–1023) are for the most important and widely used services. On many 
Unix-like operating systems, normal user programs cannot listen on these ports. In the old 
days, this prevented troublesome undergraduates on multiuser university machines from 
running programs that masqueraded as important system services. Today the same caution 
applies when hosting companies hand out command-line Linux accounts.

* Registered ports (1024–49151) are not usually treated as special by operating systems—any 
user can write a program that grabs port 5432 and pretends to be a PostgreSQL database, for 
example—but they can be registered by IANA for specific services, and IANA recommends you 
avoid using them for anything but their assigned service.

* The remaining port numbers (49152–65535) are free for any use. They, as you will see, are the 
pool on which modern operating systems draw in order to generate arbitrary port numbers 
when a client does not care what port it is assigned for its outgoing connection.