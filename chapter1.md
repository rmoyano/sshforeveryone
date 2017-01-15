#SSH 

SSH is a protocol.
With the increase o

OpenSSH is the open implementation of this protocol and it is distributed under a BSD license.


Para poder iniciarse en la programación en Haskell, proponemos que su estudio como las pruebas que 
se consideren necesarias, se realicen en los equipos particulares. Por lo tanto se hace necesario 
descargar e instalar el conjunto de librerías, ambiente interactivo y compilador correspondiente.
Dentro de los proyetos de software libre disponibles, la cátedra ha elegido una de las distribuciones
más activas de la comunidad de programación llamada Glasgow Haskell Compiler (GHC). 
Mas precisamente, al hacer referencia a *GHC*, debemos relacionarlo con un compilador optimizado para 
generar código nativo y *GHCi*, hace referencia al ambiente y depurador interactivo.

##Testing environment##
In the examples we will be using the following especifications:
- Operative System: Debian GNU/Linux 8.6 (Jessy stable).
- OpenSSH client version: 1:6.7p1-5+deb8u3

##Installation##

##GNU/Linux
For Debian OS, SSH client installation wila instalación de Haskell se realizará en la distribución Debian
que dispone del gestor de paquetes APT. In distribuciones derivadas like Ubuntu, 
Trisquel, Linux Mint, etc. the procedure is very similar and should be pretty straightforward.
For other distributions like Centos, Fedora, Mageia, etc. the procedure could be similar but
it fits to their owns package managers.

###Steps:

1. Configurar las fuentes del gestor de paquetes (APT) editando el archivo sources.list:
```bash
# vi /etc/apt/sources.list
```
2. Agregar alguno de los repositorios de Argentina:
```bash
   deb http://mirrors.dcarsat.com.ar/debian/ stable main contrib non-free
   deb-src http://mirrors.dcarsat.com.ar/debian/ stable main contrib non-free
```
3. Actualizar el índice de paquetes para verificar que se tiene conectividad con el repositorio de Debian:
```bash
   # apt-get update
```
4. Buscar los paquetes de GHC (Glasgow Haskell Compiler): 
```bash
   # apt-cache search glasgow
   bnfc - Compiler front-end generator based on Labelled BNF
   ghc - The Glasgow Haskell Compilation system
   ghc-doc - Documentation for the Glasgow Haskell Compilation system
   ghc-dynamic - Dynamic libraries for the Glasgow Haskell Compilation system
   ghc-prof - Profiling libraries for the Glasgow Haskell Compilation system
```
5. Instalar las librerías y sus respectivas dependencias:
```ShellSession
   # apt-get install ghc
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
6. Para verificar la instalación exitosa, abra una consola y ejecute el ambiente interativo de Haskell:
```Shell
   $ ghci
   Prelude>
```
