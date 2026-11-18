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

<img width="850" height="157" alt="image" src="https://github.com/user-attachments/assets/045b62e5-ed32-46e0-9870-646e5b2f5315" />
<img width="821" height="127" alt="image" src="https://github.com/user-attachments/assets/bfb4fc22-f11b-428a-818d-61e9335719b9" />
<img width="592" height="170" alt="image" src="https://github.com/user-attachments/assets/00f4f5a6-7fcd-4f8b-b10c-37b35352e1b5" />
<img width="537" height="122" alt="image" src="https://github.com/user-attachments/assets/66beedfa-90f6-45be-9927-041db07d87ce" />


## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was successfully created and executed.
