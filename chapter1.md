# What is SSH? 

*SSH* (Secure Shell) is a secure protocol for operating networks services securely over unsecured 
networks. It was designed as a replacement for old protocols like Telnet, rlogin, rsh, etc.
These network protocols allows us to remote logging in to a computer from another computer, over a network.
The main problem with these old protocols is that all the traffic travels in plain text with all the security 
issues that could be involved.

Unix and GNU/Linux operating systems, usually present a command-line interface to the user (The shell), 
much like the *Command Prompt* in Windows. The system prints a prompt, and you type commands which the 
system will execute.

Using the shell and having the right user access levels, there is no need for you to be sitting at the same
 machine you are typing commands to. You can sit at one computer, run a client which makes a network connection
to the other computer (The server) and send these commands and responses over the network. 
With SSH, once the network connection is stablished, all the traffic travels encrypted through the network. SSH carries 
your commands from the client to the server, and carries the server's responses back to you.

##OpenSSH
[OpenSSH](https://www.openssh.com/ "OpenSSH") is a fork of the original project *free ssh 1.2.12 release* from 
Tatu Ylönen. It is the open implementation of this protocol and tools designed and maintained by the same developers 
of the OpenBSD project. That is why it is distributed under a BSD license and follows the same principles with the 
focus on security.

Last version *7.4* was released December 19, 2016.

##Tools
This is the list of tools that we are going to use on this guide:

    Remote operations are done using ssh, scp, and sftp.
    Key management with ssh-add, ssh-keysign, ssh-keyscan, and ssh-keygen.
    The service side consists of sshd, sftp-server, and ssh-agent. 

- *ssh(1)* - The basic rlogin/rsh-like client program
- *sshd(8)* - The daemon that permits you to log in
- *ssh-agent(1)* - An authentication agent that can store private keys
- *ssh-add(1)* - Tool which adds keys to in the above agent
- *sftp(1)* - FTP-like program that works over SSH1 and SSH2 protocol
- *scp(1)* - File copy program that acts like rcp
- *ssh-keygen(1)* - Key generation tool
- *sftp-server(8)* - SFTP server subsystem (started automatically by sshd)
- *ssh-keyscan(1)* - Utility for gathering public host keys from a number of hosts
- *ssh-keysign(8)* - Helper program for host-based authentication

##Testing environment##
In the examples we will be using the following software versions:
Client machine
- *Operative system*: Debian GNU/Linux 8.6 Jessie (Stable).
- *OpenSSH client*: 1:6.7p1-5+deb8u3
Server machine
We are goint to use OpenBSD as server because it is the main operative
system where OpenSSH is developed and tested.  
2- Because I want to show interoperability
3- Because I use this OS. 

- *Operative system*: OpenBSD 6.0.
- *OpenSSH server*: 1:6.7p1-5+deb8u3
