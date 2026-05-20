# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
###Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
###Sever
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
Client
<img width="940" height="357" alt="image" src="https://github.com/user-attachments/assets/bc6809bb-6675-4b10-8ad4-b3cb88b8f1fc" />

Server
<img width="857" height="308" alt="image" src="https://github.com/user-attachments/assets/bdedc6e0-4f28-4d17-afa9-5ebef3d6cd21" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
