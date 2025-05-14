# 4.Execution_of_NetworkCommands
## AIM :
Use of Network commands in Real Time environment
## Software : 
Command Prompt And Network Protocol Analyzer
## Procedure:
To do this EXPERIMENT- follows these steps:
<BR>
In this EXPERIMENT- students have to understand basic networking commands e.g cpdump, netstat, ifconfig, nslookup ,traceroute and also Capture ping and traceroute PDUs using a network protocol analyzer 
<BR>
All commands related to Network configuration which includes how to switch to privilege mode
<BR>
and normal mode and how to configure router interface and how to save this configuration to
<BR>
flash memory or permanent memory.
<BR>
This commands includes
<BR>
* Configuring the Router commands
<BR>
* General Commands to configure network
<BR>
* Privileged Mode commands of a router 
<BR>
* Router Processes & Statistics
<BR>
* IP Commands
<BR>
* Other IP Commands e.g. show ip route etc.
<BR>

## Program :
### Client :
```python
import socket 
from pythonping import ping 
s=socket.socket() 
s.bind(('localhost'8000)) 
s.listen(5) 
c,addr=s.accept() 
while True: 
    hostname=c.recv(1024).decode() 
    try: 
        c.send(str(ping(hostname, verbose=False)).encode()) 
    except KeyError: 
        c.send("Not Found".encode())
```
### Server :
```python
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    ip=input("Enter the website you want to ping ") 
    s.send(ip.encode()) 
    print(s.recv(1024).decode())
```
### Traceroute Command :
```python
from scapy.all import* 
target = ["www.google.com"] 
result, unans = traceroute(target,maxttl=32) 
print(result,unans)
```
## Output :
### Client :
![img1](https://github.com/gowshik145/4.Execution_of_NetworkCommends/assets/155086127/6de5d071-4fb7-48db-807d-f0482ce92c82)

### Server :
![ex 4 img2](https://github.com/gowshik145/4.Execution_of_NetworkCommends/assets/155086127/d99e2896-0db4-4ff3-a6ba-77a0acf13069)

### Traceroute :
![ex 4 img 3](https://github.com/gowshik145/4.Execution_of_NetworkCommends/assets/155086127/15971767-a723-4f50-9007-947f3548c7dc)

## Result :
Thus Execution of Network commands Performed 
