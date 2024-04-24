## Ex.No:2a Stop and wait protocol

## AIM:
To write a python program to perform stop and wait protocol.

## ALGORITHM:
1. Start the program.
   
2. Get the frame size from the user.
  
3. To create the frame based on the user request.
   
4. To send frames to server from the client side.
   
5. If your frames reach the server it will send ACK signal to client.
   
6. Stop the Program.
   
## PROGRAM:
# Client
~~~
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
~~~

# Server
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Received".encode())
~~~

## OUTPUT:
# Client
![image](https://github.com/K-Dharshini/2a_Stop_and_Wait_Protocol/assets/139334830/280cdb0b-10a2-4e5d-b626-4bc44a2e44da)

# Server
![image](https://github.com/K-Dharshini/2a_Stop_and_Wait_Protocol/assets/139334830/f67370e2-9492-4781-8d83-ec704fefba93)

## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
