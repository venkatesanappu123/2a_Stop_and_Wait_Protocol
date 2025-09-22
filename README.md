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
# Server.py
```
import socket
s=socket.socket()
s.bind(("localhost",8000))
s.listen(5)

c,add=s.accept()
while True:
    
    i=input("Enter a data:" )
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```
# Client.py
```
import socket
s=socket.socket()
s.connect(("localhost",8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT

<img width="959" height="480" alt="Screenshot 2025-09-22 151109" src="https://github.com/user-attachments/assets/34fa88bf-527b-46ad-b4dc-84a73f938c57" />

<img width="959" height="481" alt="Screenshot 2025-09-22 151131" src="https://github.com/user-attachments/assets/b97b95c2-bcd9-45dd-b524-58a0dfcda951" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
