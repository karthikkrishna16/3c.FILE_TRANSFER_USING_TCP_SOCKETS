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
### NAME : TH KARTHIK KRISHNA
### REG NO : 212223240067

## CLIENT
```
import socket
s = socket.socket()
host = socket.gethostname()
port = 60000
s.connect((host, port))
s.send("Hello server!".encode())
with open('received_file', 'wb') as f:
print('receiving data...')
while True:
data = s.recv(1024)
print('data=%s', (data))
if not data:
break
f.write(data)
print('Successfully received the file')
s.close()
print('connection closed')
```
## SERVER
```
import socket
port = 60000
s = socket.socket()
host = socket.gethostname()
s.bind((host, port))
s.listen(5)
print("Server listening on port", port)
while True:
conn, addr = s.accept()
print("Connected to", addr)
data = conn.recv(1024)
print('Server received', repr(data))
filename = 'C:\\Users\\admin\\OneDrive\\Desktop\\mytext.txt'
with open(filename, 'rb') as f:
l = f.read(1024)
while l:
conn.send(l)
print('Sent', repr(l))
l = f.read(1024)
print('Done sending')
conn.send('Thank you for connecting'.encode())
conn.close()
```
## OUPUT
![WhatsApp Image 2024-04-29 at 14 04 00_5a3102f7](https://github.com/DEVAABISHEK/3c.FILE_TRANSFER_USING_TCP_SOCKETS/assets/150319305/7b21c0c3-ce74-4a22-bd81-1f25a54fb20b)
![WhatsApp Image 2024-04-29 at 13 56 02_79ac47d3](https://github.com/DEVAABISHEK/3c.FILE_TRANSFER_USING_TCP_SOCKETS/assets/150319305/36a9abd4-ce39-49a5-b66b-6d6088505e2c)
## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
