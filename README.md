# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### Name: Vikaash K S
### Register Number: 212223240179
### Date: 03.09.2024
## AIM:
To write a python program for Implementation of sliding Window Protocol.

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM:
### Client
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
### Server
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
  st+=s
  c.send(str(l[i:st]).encode())
  ack=c.recv(1024).decode()
  if ack:
   print(ack)
   i+=s
```
<br> <br> <br>
## OUPUT:
### Client
![exp 2b client](https://github.com/user-attachments/assets/813b2b66-c154-47ae-ba05-a558b811eaf5)

### Server
![exp 2b server ](https://github.com/user-attachments/assets/d51d24a4-9ead-4fe9-bd5b-180d4e245f56)

## RESULT
Thus, python program to perform sliding window protocol was successfully executed
