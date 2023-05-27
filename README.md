## EX-6 IMPLEMENTATION OF PING COMMAND
```
DATE : 13-04-2023
```
### AIM :
To write the python program for simulating ping command.
### ALGORITHM :
```
1. Start the program.
2. Include necessary package in java.
3. To create a process object p to implement the ping command.
4. Declare one Buffered Reader stream class object.
5. Get the details of the server
6. Length of the IP address.
7. Time required to get the details.
8. Send packets, receive packets and lost packets.
9. Minimum, maximum and average times.
10. Print the results.
11. Stop the program.
```
### PROGRAM :
```
Developed : G Venkata Pavan Kumar
Reg.No. : 212221240013
```
#### Client Side:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
#### Server Side:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
### OUTPUT :
#### Client Side:
![image](https://github.com/Pavan-Gv/EX-6/assets/94827772/4c043989-1ce8-4a79-a6b0-5b3d7b260c58)
#### Server Side:
![image](https://github.com/Pavan-Gv/EX-6/assets/94827772/10f5575f-6ecc-41e6-a9c9-e5a17e5ebee4)
### RESULT :
Thus, the python program for simulating ping command was successfully executed.

