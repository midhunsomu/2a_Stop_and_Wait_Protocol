# 2a_Stop_and_Wait_Protocol

### Name: Midhun S
### Reg.no:212223240087


## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM:
## Client Program:
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
## Server Program:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
<br><br><br>
<br><br><br>
<br><br><br>
<br><br><br>

## OUTPUT
### CLIENT
![client](https://github.com/user-attachments/assets/db543433-0db9-4029-9652-a575506177f1)

### SERVER
![server](https://github.com/user-attachments/assets/ed1ae856-6878-46c2-9511-f1cca4d48cab)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
