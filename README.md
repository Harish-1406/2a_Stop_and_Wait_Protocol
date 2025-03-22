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
server.py
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

client.py
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT
![Screenshot 2025-03-22 154239](https://github.com/user-attachments/assets/a0c61e12-c1d0-4050-aaa5-e2f004460d39)
![Screenshot 2025-03-22 154250](https://github.com/user-attachments/assets/23941c5a-2e04-4b14-a8d2-a5a20d21132f)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
