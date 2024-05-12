# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

### Name: POOJA A
### Register No: 212222240072
### Date: 12-05-2024

## AIM
To implent the program for the implementation of sliding window protocol

## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program


## PROGRAM
### Client:
```python
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

### Server:
```python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
    print(s.recv(1024).decode())
    s.send("acknowledgement recived from the server".encode())
```

## OUTPUT

![319868298-c17b89e0-ed9b-4f9c-9ccf-1d14c7d862a7](https://github.com/poojaanbu0/2b_SLIDING_WINDOW_PROTOCOL/assets/119390329/0a8431d3-0dc9-4744-a872-6d78e3ec7e96)

## RESULT
Thus, python program to perform sliding window protocol was successfully executed
