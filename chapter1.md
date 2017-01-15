# What is SSH? 

SSH (Secure Shell) is a protocol designed to be a replacement for old plain text protocols like Telnet.
With the increase o

OpenSSH is the open implementation of this protocol created by the same developers of the OpenBSD project. 
That is why it is distributed under a BSD license and follows the same principles with the security on concern.

##Testing environment##
In the examples we will be using the following software versions:
- Operative system: Debian GNU/Linux 8.6 Jessy (Stable).
- OpenSSH client: 1:6.7p1-5+deb8u3

##Installation##

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
   Leyendo lista de paquetes... Hecho
   Creando árbol de dependencias       
   Leyendo la información de estado... Hecho
   Se instalarán los siguientes paquetes extras:
       binutils cpp cpp-4.9 gcc gcc-4.9 libasan0 libasan1 libatomic1 libbsd-dev libcilkrts5
       libcloog-isl4 libffi-dev libgcc-4.8-dev libgcc-4.9-dev libgmp-dev libgmpxx4ldbl libgomp1
       libisl10 libitm1 liblsan0 libmpc3 libmpfr4 libquadmath0 libstdc++-4.8-dev libtsan0 libubsan0
   Paquetes sugeridos:
       binutils-doc cpp-doc gcc-4.9-locales gcc-multilib make autoconf automake libtool flex bison
       gdb gcc-doc gcc-4.9-multilib gcc-4.9-doc libgcc1-dbg libgomp1-dbg libitm1-dbg libatomic1-dbg
       libasan1-dbg liblsan0-dbg libtsan0-dbg libubsan0-dbg libcilkrts5-dbg libquadmath0-dbg
       ghc-prof ghc-doc haskell-doc llvm libgmp10-doc libmpfr-dev libstdc++-4.8-doc
   Se instalarán los siguientes paquetes NUEVOS:
       binutils cpp cpp-4.9 gcc gcc-4.9 ghc libasan0 libasan1 libatomic1 libbsd-dev libcilkrts5
       libcloog-isl4 libffi-dev libgcc-4.8-dev libgcc-4.9-dev libgmp-dev libgmpxx4ldbl libgomp1
       libisl10 libitm1 liblsan0 libmpc3 libmpfr4 libquadmath0 libstdc++-4.8-dev libtsan0 libubsan0
   0 actualizados, 27 nuevos se instalar�n, 0 para eliminar y 23 no actualizados.
   Se necesita descargar 47,1 MB de archivos.
   Se utilizarán 384 MB de espacio de disco adicional después de esta operación.
   ¿Desea continuar? [S/n]
```
6. Open the shell and execute the following command to check if it is installed:
```Shell
   $ ssh -V
   OpenSSH_6.7p1 Debian-5+deb8u3, OpenSSL 1.0.1t  3 May 2016
```
