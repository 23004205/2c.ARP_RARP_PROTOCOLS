# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## CLIENT:
1. Start the program

2. Using socket connection is established between client and server.

3. Get the IP address to be converted into MAC address.

4. Send this IP address to server.

5. Server returns the MAC address to client.
## SERVER:
1. Start the program

2. Accept the socket which is created by the client.

3. Server maintains the table in which IP and corresponding MAC addresses are
stored.

4. Read the IP address which is send by the client.

5. Map the IP address with its MAC address and return the MAC address to client.
## PROGRAM - ARP
### CLIENT:
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
### SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
### CLIENT:
![image](https://github.com/Thilak45/2c.ARP_RARP_PROTOCOLS/assets/138849161/cf122ab8-e63e-42d3-b029-1656297fa2e2)
### SERVER:
![image](https://github.com/Thilak45/2c.ARP_RARP_PROTOCOLS/assets/138849161/b88377f2-02c8-4585-8769-7e9b4534027e)
### ALGORITHM FOR RARP
### CLIENT:
1.Start the program

2.Using datagram sockets UDP function is established.

3.Get the MAC address to be converted into IP address.

4.Send this MAC address to server.

5.Server returns the IP address to client.
### SERVER:
1.Start the program.

2.Server maintains the table in which IP and corresponding MAC addresses are stored.

3.Read the MAC address which is send by the client.

4.Map the IP address with its MAC address and return the IP address to client.
## PROGRAM - RARP
### CLIENT:
```
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())
```
### SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode())
## OUPUT -RARP
```
### CLIENT:
![image](https://github.com/Thilak45/2c.ARP_RARP_PROTOCOLS/assets/138849161/bf0f5e38-5d63-4f25-9cf8-3d7beb1bf011)
### SERVER:
![image](https://github.com/Thilak45/2c.ARP_RARP_PROTOCOLS/assets/138849161/5c3c398b-fd73-4e19-82f1-e07e624e558a)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
