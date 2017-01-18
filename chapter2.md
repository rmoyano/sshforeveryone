# SSH client installation
Firstly, we need the software installed in order to start the tests. SSH follows a client-server 
architecture, so we need a client installed in one computer and the daemon waiting for 
connections on other machine that is working as server.     

   ![Architecture.](/images/client-server.png "Client-server")

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
2. Add one mirror that is located close to your city or country:
```bash
   deb http://mirrors.dcarsat.com.ar/debian/ stable main contrib non-free
   deb-src http://mirrors.dcarsat.com.ar/debian/ stable main contrib non-free
```
3. Update the package index in order to verify that the Debian mirrors are online:
```bash
   # apt-get update
```
4. Search for ssh client and server: 
```bash
   # apt-cache search ssh-client
   devscripts - scripts to make the life of a Debian Package maintainer easier
   openssh-client - secure shell (SSH) client, for secure access to remote machines
   ssh-askpass-gnome - interactive X program to prompt users for a passphrase for ssh-add

   # apt-cache search ssh-server
   dropbear - lightweight SSH2 server and client
   lsh-server - Secure Shell v2 (SSH2) protocol server
   task-ssh-server - SSH server
   openssh-server - secure shell(SSH) server, for secure access from remote machines
```
5. Install the software with their dependences:
```ShellSession
   # apt-get install oepnssh-client openssh-server
   Reading package lists... Done
   Builduing dependency tree       
   Reading state information... Done
   The following extra packages will be installed:
   openssh-sftp-server
   Suggested packages:
       ssh-askpass rssh molly-guard ufw monkeysphere
   The following new packages will be installed:
       openssh-client openssh-server openssh-sftp-server
   0 upgraded, 2 newly installed, 0 to remove y 23 not upgraded.
   Need to get 878kB of files.
   After this operation, 1810kB of additional disk space will be used.
   ¿Do you wanto to continue? [Y/n]Y
```
6. Open the shell and execute the following command to check if it is installed:
```Shell
   $ ssh -V
   OpenSSH_6.7p1 Debian-5+deb8u3, OpenSSL 1.0.1t  3 May 2016
```

##Microsoft Windows
The most famous and widely used SSH client for Windows is Putty. PuTTY is a free implementation of SSH and 
Telnet for Windows. 

###Steps:
1. Go to official [PuTTY's](http://www.chiark.greenend.org.uk/~sgtatham/putty/ "PuTTY") project page.

2. Click on [Download](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html "Download") section.
   
3. In the *Binaries* section you have different download options. I think the best option for this case is to choose 
the MSI installer package, because you get all the tools that we will use:

   ![Binaries.](/images/binaries.png "Binaries")

4. Select [MSI installer](https://the.earth.li/~sgtatham/putty/latest/x86/putty-0.67-installer.msi) and choose to save the file: 

   ![MSI installer.](/images/msi_installer.png "MSI installer")
                  
5. Once the download has finished, execute the installer and click *Next* button an infinite number of times until 
   you complete the installation.
