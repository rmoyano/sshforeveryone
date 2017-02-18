# Basic commands

   ![Example.](/images/solca_vps.png "Example")

## SSH 
SSH is the main command that we are going to use for the rest of our lives. 

Our company runs a web system using www.solca.com URL. 
Let say that we have our own VPS located in Norway and we need to change the web server database engine. 
We can not travel to Oslo every time that we need to make changes, this is where SSH enters.

The basic SSH syntax is the following: 
```bash
   rafa@host:~/sshforeveryone$ ssh rafa@solca.com
   The authenticity of host 'solca.com (201.12.24.48)' can't be established.
   ECDSA key fingerprint is 8b:5e:99:85:28:f1:95:25:c6:bc:cc:2e:56:e7:18:a3.
   Are you sure you want to continue connecting (yes/no)? yes
   Warning: Permanently add ed 'solca.com,201.12.24.48' (ECDSA) to the list of known hosts.
   rafa@solca.com's password: 

   Debian GNU/Linux 8

   rafa@solcaserver:~$ uname -a
   Linux solcaserver 3.16.0-4-amd64 #1 SMP Debian 3.16.36-1+deb8u2 (2016-10-19) x86_64 GNU/Linux
   rafa@solcaserver:~$ exit
   logout
   Connection to solca.com closed.
```
Where rafa is the username and the rest after *@* is the remote server's URL.

If you know the server's IP, we can use it instead:
```bash
   rafa@host:~/sshforeveryone$ ssh rafa@201.12.24.48

   rafa@201.12.24.48's password: 

   Debian GNU/Linux 8

   rafa@solcaserver:~$ exit
   logout
   Connection to solca.com closed.
```

SSH server default listening port is 22 but the main problem with that is that every bot on the net is trying to 
enter testing it. So, we have changed the listening port to 2345.

To change the default listening port we need to add the port argument *-p* in the command:
```bash
   rafa@host:~/sshforeveryone$ ssh -p 2345 rafa@201.12.24.48
```
You can type port argument at the end of the sentence too:

```bash
   rafa@host:~/sshforeveryone$ ssh rafa@201.12.24.48 -p 2345 
```
