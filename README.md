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
## Client :
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
## Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT:
## Client Output:
![Client](https://github.com/DaisyRavi/2a_Stop_and_Wait_Protocol/assets/151394386/9e99ea0a-b99b-4bc6-81eb-90109e577602)

## Server Output:
![Server (2)](https://github.com/DaisyRavi/2a_Stop_and_Wait_Protocol/assets/151394386/8a0e6ad0-9849-4565-b761-e66e7efd91da)
![Screenshot 2024-03-07 170527](https://github.com/DaisyRavi/2a_Stop_and_Wait_Protocol/assets/151394386/738bf0e1-7042-4e7e-92ee-2d04be8b3e4c)
## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
