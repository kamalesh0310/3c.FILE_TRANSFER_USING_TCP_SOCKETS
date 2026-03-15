# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
Server.py
~~~
mport socket
server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = "127.0.0.1"
port = 12345
server.bind((host, port))
server.listen(1)
print("Server waiting for connection...")
conn, addr = server.accept()
print("Connected to:", addr")
file = open("sample.txt", "rb")
data = file.read()
conn.send(data)
print("File sent successfully")
file.close()
conn.close()
~~~
Client.py
~~~
import socket
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
host = "127.0.0.1"
port = 12345
client.connect((host, port))
data = client.recv(1024)
file = open("received.txt", "wb")
file.write(data)
print("File received successfully")
file.close()
client.close()
~~~
## OUPUT
server:

client:

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
