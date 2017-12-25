# python-shell
## What Is A Shell

A shell is acts as an interface between the user and Operating system. You can use a shell to do many things such as view files, launch applications,  check network configurations, etc. Some examples would be Powershell in Windows and the Terminal in Linux.

## Reverse vs Bind Shells

The reverse and bind shells both have the same purpose, to allow for remote access to a computer. The difference between the two is how the connection is initiated. A bind shell acts as a server on the target meaning the attacker has to connect to it. The reverse shell acts as a client, meaning the attacker needs to set up a server to allow the reverse shell to connect back.

## Why use Reverse Shells?

If both shells serve the same purpose why are reverse shells generally considered better? Reverse shells are favored more mainly due to how a firewall acts. Generally a firewall will not allow a non admin/root program to open a lower port number. They also usually attempt to stop any application that makes the computer act as a server and block any incoming connections. However, a reverse shell connects to the attacker and a firewall generally won’t block outgoing connections, otherwise the user may not be able to access the net. The reverse shell has the advantages of bypassing the firewall AND running without admin/root.

## How the code will work

The code will utilize two standard library python modules, socket and subprocess. The attackers server will wait on a specific port for the reverse shell to connect back. Once a connection is initiated, the attacker sends a string to the reverse shell which will then take that string and execute it as a system command before returning the output. The best part is that it is FUD(Fully undetectable) as this is coded in a interpreted language. However you CAN compile the script into a windows executable using pyinstaller so it can run without the interpreter.


Compiling to a windows executable

Since python scripts can’t run without the interpreter, you need to use a tool called pyinstaller ,which is NOT included with the default python installation, to convert the script into a windows executable. We are going to save the client code as client.py. Open a local system shell and type in :

```pyinstaller –windowed –onefile client.py```

This created a packed python executable that runs without a visible GUI window so the user is not alerted to anything suspicious.

Conclusion

This is not all that the reverse shell can do. The one we coded is extremely basic. However you can code more and more complex reverse shells. I have created reverse shells that have even more functionality such as file transfer, keylogging and screenshotting. This is not all that you are limited to. If you want to see examples of much more complex reverse shells you can visit my Github Repo :

https://www.github.com/ahirejayeshbapu/python-shell



 

Have fun, anything is possible :).
