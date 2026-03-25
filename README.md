# 4.Execution_of_NetworkCommands
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
##Program

Server.py
import socket
from pythonping import ping
s = socket.socket()
# Bind to localhost and port
s.bind(('localhost', 8000))
# Listen for connections
s.listen(5)
print("Ping Server started... Waiting for connection")
# Accept connection
c, addr = s.accept()
print("Connected to:", addr)
while True:
    hostname = c.recv(1024).decode()
    if not hostname:
        break
    try:
        result = ping(hostname, count=4, verbose=False)
        c.send(str(result).encode())
    except:
        c.send("Host Not Found".encode())
c.close()

Client.py
import socket
# Create socket
s = socket.socket()
# Connect to server
s.connect(('localhost', 8000))
while True:
    website = input("Enter the website you want to ping: ")
    if website.lower() == "exit":
        break
    s.send(website.encode())
    result = s.recv(1024).decode()
    print("\nPing Result:\n", result)
s.close()

Traceroute.py
import os
print("Running Traceroute...\n")
os.system("C:\\Windows\\System32\\tracert.exe google.com")


## Output
1.ping

<img width="1127" height="456" alt="image" src="https://github.com/user-attachments/assets/108396dd-f15e-4c22-bdc1-3f7e06ae8d71" />

2)Tracert

<img width="809" height="423" alt="image" src="https://github.com/user-attachments/assets/2aae26db-f4e0-4651-9578-f73d40f13851" />

3)ipconfig

<img width="790" height="583" alt="image" src="https://github.com/user-attachments/assets/f00166ca-c055-4850-9013-492c3272dc61" />

4)netstat

<img width="808" height="793" alt="image" src="https://github.com/user-attachments/assets/22f777ae-1a29-4d28-8a65-c8699139bbe2" />

5)nslookup

<img width="778" height="559" alt="image" src="https://github.com/user-attachments/assets/f629e831-ab85-4e1c-99d1-c0ccdd33f408" />

6)getmac

<img width="795" height="152" alt="image" src="https://github.com/user-attachments/assets/28f6baa5-1904-4248-ac4c-10e228d09dbf" />

7)nbtstat

<img width="800" height="430" alt="image" src="https://github.com/user-attachments/assets/70d37d3b-7145-4e3d-8c9e-296f1e4f5496" />

8)arp

<img width="815" height="658" alt="image" src="https://github.com/user-attachments/assets/a5dfb7f2-a91f-4c5d-9d22-9b6ccea0065f" />

9)systeminfo

<img width="954" height="849" alt="image" src="https://github.com/user-attachments/assets/51489afd-5929-4844-b19f-f49f90d532c2" />
<img width="792" height="410" alt="image" src="https://github.com/user-attachments/assets/3475c875-4ddd-4251-8082-7f076640d4d9" />



## Result
Thus Execution of Network commands Performed 
