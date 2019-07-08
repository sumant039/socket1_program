# socket1_program

Socket programming is a way of connecting two nodes on a network to communicate with each other. 
One socket(node) listens on a particular port at an IP, while other socket reaches out to the other to form a connection. 
Server forms the listener socket while client reaches out to the server.
They are the real backbones behind web browsing. In simpler terms there is a server and a client. 
Socket programming is started by importing the socket library and making a simple socket.
import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
Here we made a socket instance and passed it two parameters. 
The first parameter is AF_INET and the second one is SOCK_STREAM. AF_INET refers to the address family ipv4.
 The SOCK_STREAM means connection oriented TCP protocol. 
Now we can connect to a server using this socket.



Server :
A server has a bind() method which binds it to a specific ip and port so that it can listen to incoming requests on that ip and port.
A server has a listen() method which puts the server into listen mode. This allows the server to listen to incoming connections.
 And last a server has an accept() and close() method. 
The accept method initiates a connection with the client and the close method closes the connection with the client

First of all we import socket which is necessary.
Then we made a socket object and reserved a port on our pc.
After that we binded our server to the specified port. 
Passing an empty string means that the server can listen to incoming connections from other computers as well. 
If we would have passed 127.0.0.1 then it would have listened to only those calls made within the local computer.
After that we put the server into listen mode.5 here means that 5 connections are kept waiting if the server is busy and if a 6th socket trys to connect then the connection is refused.
At last we make a while loop and start to accept all incoming connections and close those connections after a thank you message to all connected sockets.

Client:

Now we need something with which a server can interact. We could tenet to the server like this just to know that our server is working. Type these commands in the terminal:
# start the server
$ python server.py


First of all we make a socket object.
Then we connect to localhost on port 12345 (the port on which our server runs) and lastly we receive data from the server and close the connection.
Now save this file as client.py and run it from the terminal after starting the server script.