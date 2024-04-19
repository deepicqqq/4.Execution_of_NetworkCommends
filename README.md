# 4.Execution_of_NetworkCommands
NAME:DEEPIKA P
REFERENCE NO:212223240024
## AIM :Use of Network commands in Real Time environment
## Software : Command Prompt And Network Protocol Analyzer
## Procedure: To do this EXPERIMENT- follows these steps:
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
• Configuring the Router commands
<BR>
• General Commands to configure network
<BR>
• Privileged Mode commands of a router 
<BR>
• Router Processes & Statistics
<BR>
• IP Commands
<BR>
• Other IP Commands e.g. show ip route etc.
<BR>

## PROGRAM:
## Ping Command:
## CLIENT:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8100))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8100))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
## Tracert Command:
```
from scapy.all import*
target = ["www.google.com"]
result, unans = traceroute(target,maxttl=32)
print(result,unans)

```
## Output:
## Ping Command:
![Screenshot 2024-04-06 093832](https://github.com/ANU23000217/4.Execution_of_NetworkCommends/assets/139117108/271abaea-5705-4a3a-9c4a-1ce5c17b8c41)

## Tracert Command:
![Screenshot 2024-04-18 205544](https://github.com/ANU23000217/4.Execution_of_NetworkCommends/assets/139117108/785a31e7-41c5-43b0-a47d-39f00af77ac2)

## Result:
Thus Execution of Network commands Performed 
