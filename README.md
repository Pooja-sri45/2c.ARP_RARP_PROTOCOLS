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
## PROGRAM - ARP



CLIENT
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




SERVER
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
![image](https://github.com/Pooja-sri45/2c.ARP_RARP_PROTOCOLS/assets/147081893/1eb2c48c-970b-4ee8-9a24-8779dbbefdee)
![image](https://github.com/Pooja-sri45/2c.ARP_RARP_PROTOCOLS/assets/147081893/3d69a327-643e-4142-aa1f-e4d9dd5c1fd1)



ALGORITHM FOR RARP:
CLIENT
1.Start the program
2.Using datagram sockets UDP function is established.
3.Get the MAC address to be converted into IP address.
4.Send this MAC address to server.
5.Server returns the IP address to client.


SERVER
1.Start the program.
2.Server maintains the table in which IP and corresponding MAC addresses are stored.
3.Read the MAC address which is send by the client.
4.Map the IP address with its MAC address and return the IP address to client.



## PROGRAM - RARP

CLIENT
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
SERVER

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
![image](https://github.com/Pooja-sri45/2c.ARP_RARP_PROTOCOLS/assets/147081893/5f8bdf82-5e3a-406c-a573-1f0eeea02a6b)
![image](https://github.com/Pooja-sri45/2c.ARP_RARP_PROTOCOLS/assets/147081893/0ffded47-9e92-461d-80af-3ae3712f2315)





## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
