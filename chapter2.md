# SSH client installation

##GNU/Linux
For Debian OS, SSH client is installed by default but if that is not the case, we will use Debian's package
manager called APT. In Debian based distributions like Ubuntu, Trisquel, Linux Mint, etc. the procedure is 
very similar and should be pretty straightforward.
For other distributions like Centos, Fedora, Mageia, Gentoo, etc. the procedure could be similar but
you will need to use their owns package managers (RPM, Portage, etc.).

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
5. Install the client and their dependences:
```ShellSession
   # apt-get install ssh-client
   Reading package lists... Done
   Builduing dependency tree       
   Reading state information... Done
   Suggested packages:
       openshh-server
   The following new packages will be installed:
       openssh-client 
   0 upgraded, 1 newly installed, 0 to remove y 23 not upgraded.
   Need to get 878kB of files.
   After this operation, 810kB of additional disk space will be used.
   ¿Do you wanto to continue? [Y/n]Y
```
6. Open the shell and execute the following command to check if it is installed:
```Shell
   $ ssh -V
   OpenSSH_6.7p1 Debian-5+deb8u3, OpenSSL 1.0.1t  3 May 2016
```
