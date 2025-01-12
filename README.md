# EX-4 IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)
# DATE :28-03-2023
# Developed by: Lavanya S
# Reg.No:212221220030
# AIM :
To write a python program for simulating ARP protocols using TCP

# ALGORITHM :
# Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
# Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
# PROGRAM :
# Client:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
        ```
# SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
    ```
# OUTPUT :
# Client:
![image](https://github.com/LavanyaSIT/EX-4/assets/130207418/d9818371-75f0-4276-be56-afff561bba01)

# Server:
![image](https://github.com/LavanyaSIT/EX-4/assets/130207418/2d5e4fe4-de68-4fd1-a73c-0aeeb3223235)


# RESULT :
Thus, the python program for simulating ARP protocols using TCP was successfully executed.

