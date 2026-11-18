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
server.py
~~~
import socket

s = socket.socket()
s.bind(('localhost', 12345))
s.listen(1)

print("Waiting for client...")
c, addr = s.accept()

f = open("sample.txt", "rb")
data = f.read()

c.sendall(data)

print("File sent successfully")

f.close()
c.close()
s.close()
~~~

client.py
~~~
import socket

s = socket.socket()
s.connect(('localhost', 12345))

f = open("received.txt", "wb")

while True:
    data = s.recv(1024)

    if not data:
        break

    f.write(data)

print("File received successfully")

f.close()
s.close()
~~~

sample.txt
~~~
helllo
~~~

## OUPUT
## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
