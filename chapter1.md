# What is SSH? 

SSH (Secure Shell) is a secure protocol for operating networks services securely over unsecured networks. 
It was designed as a replacement for old protocols like Telnet, rlogin, rsh, etc.

OpenSSH is the open implementation of this protocol created by the same developers of the OpenBSD project. 
That is why it is distributed under a BSD license and follows the same principles with the security on concern.

##Tools
-ssh(1) - The basic rlogin/rsh-like client program
-sshd(8) - The daemon that permits you to log in
-ssh-agent(1) - An authentication agent that can store private keys
-ssh-add(1) - Tool which adds keys to in the above agent
-sftp(1) - FTP-like program that works over SSH1 and SSH2 protocol
-scp(1) - File copy program that acts like rcp
-ssh-keygen(1) - Key generation tool
-sftp-server(8) - SFTP server subsystem (started automatically by sshd)
-ssh-keyscan(1) - Utility for gathering public host keys from a number of hosts
-ssh-keysign(8) - Helper program for host-based authentication


##Testing environment##
In the examples we will be using the following software versions:
- Operative system: Debian GNU/Linux 8.6 Jessy (Stable).
- OpenSSH client: 1:6.7p1-5+deb8u3

##Installation##

###Steps:

1. Set-up Debian mirrors in sources.list file:
```bash
# vi /etc/apt/sources.list
```
2. Add one mirror that is located close to your city or country :
```bash
   deb http://mirrors.dcarsat.com.ar/debian/ stable main contrib non-free
   deb-src http://mirrors.dcarsat.com.ar/debian/ stable main contrib non-free
```
3. Update the package index in order to verify that the Debian mirrors are online:
```bash
   # apt-get update
```
4. Search for ssh client: 
```bash
   # apt-cache search ssh-client
   openssh-client - secure shell (SSH) client, for secure access to remote machines
   ssh-askpass-gnome - interactive X program to prompt users for a passphrase for ssh-add
```
