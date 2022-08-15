<h1>Creating a Demilitarized Zone</h1>


<h2>Description</h2>
In this lab, I learned to create a demilitarized zone. DMZ (demilitarized zone) is used to secure the server's access. Servers are available through the Internet and open to all, which makes them the most vulnerable and first choice for attackers. They are also one of the most valuable assets of any company. So, we need to protect them by creating a DMZ.
<br />



<h2>Environments Used </h2>

- <b>Ubuntu 20.04.2 LTS</b> 
- <b>PuTTY SSH Client</b>

<h2>Program walk-through:</h2>

<p align="center">
From the left sidebar click PuTTY SSH Client and proceed to put in the IP address, port number, click Telnet and then click open: <br/>
<img src="https://i.postimg.cc/qqWmNCf8/Screen-Shot-2022-08-14-at-7-18-32-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
<br />
In the PC4 terminal window execute "ping 192.168.1.100"   <br/>
<img src="https://i.postimg.cc/pr2J6YfV/Screen-Shot-2022-08-14-at-7-21-52-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
  
  
  
  
<br />
Open a new window from PuTTY SSH Client and enter in the IP address, port number, click Telnet and then click open  <br/>
<img src="https://i.postimg.cc/Y07fGcbC/Screen-Shot-2022-08-14-at-7-24-07-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the R5 terminal window execute the following commands  <br/>
1. conf t <br/>
2. access-list 100 deny ip 192.168.2.101 0.0.0.255 192.168.1.0 0.0.0.255 <br/>
3. access-list 100 permit ip any any <br/>
4. interface e0/1 <br/>
5. IP access-group 100 in <br/>
6. end <br/>
<img src="https://i.postimg.cc/FHQVBDz0/Screen-Shot-2022-08-14-at-7-32-22-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />




<br />
In the R5 terminal window execute the following command "show access-lists" into to enable mode to check the access list <br/>
<img src="https://i.postimg.cc/v8641nLK/Screen-Shot-2022-08-14-at-7-36-38-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />


  
<br />
In the R5 terminal window execute the following command "show access-lists" into to enable mode to check the access list  <br/>
<img src="https://i.postimg.cc/rFV7nBF2/Screen-Shot-2022-08-14-at-7-39-25-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />
 



<br />
close the R5 terminal and in the PC4 terminal type the command "ping 192.168.1.100" to test the set up demilitarized zone (you will observe that it is not able to ping  <br/>
<img src="https://i.postimg.cc/xCJ6qbV9/Screen-Shot-2022-08-14-at-7-45-14-PM.png" height="80%" width="80%" alt="Configuring Advanced Ethernet Options Steps"/>
<br />







  
  
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
