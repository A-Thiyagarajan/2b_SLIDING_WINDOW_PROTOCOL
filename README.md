# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
##### Reg.no: 212222240110
##### Name: Thiyagarajan A
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client
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

### Server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```


## OUPUT
### Client

![2b2](https://github.com/A-Thiyagarajan/2b_SLIDING_WINDOW_PROTOCOL/assets/118707693/8fb49833-436c-457a-ae63-b62339e86754)




### Server


![2b1](https://github.com/A-Thiyagarajan/2b_SLIDING_WINDOW_PROTOCOL/assets/118707693/805567ee-f006-431d-9234-a690d8d42cbe)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
