# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P

NAME: GANESH PRABHU J

REG NO:212223220023
## PROGRAM - ARP
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
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP
![331214470-14e3988e-bf4c-40b7-abb3-c552310c66cc](https://github.com/user-attachments/assets/d527304b-2540-43df-aac8-878981aee64e)


![331214805-99c92ba3-7e8e-43f5-a0b8-1d91245f2955](https://github.com/user-attachments/assets/128b0fed-d292-414f-a947-eab13d1df5e2)


## PROGRAM - RARP
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
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP

![331215637-b01fe0b4-3af3-4513-841c-1e8dae8c4283](https://github.com/user-attachments/assets/61fa956c-621f-450a-98e1-ea733beadc92)

![331216104-abf5e051-ec1d-4d72-8919-02014d11cd0a](https://github.com/user-attachments/assets/d0b9d579-0c74-4d0b-9cdd-24066e9a03d3)



## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
