<h1>How to capture and analyse a data packet (p-cap file) using Tcpdump</h1>



<h2>Description</h2>
In this Project i used Tcpdump to check available interfaces in which i can conduct my data capturing and then went on to capture and analyse or inspect data packet file and applying filters to sort through packet information using the tcpdump command line.
<br />


<h2>Utilities Used</h2>

- <b>Tcpdump commandline interface</b>
- <b>Tcpdump</b>

<h2>Environments Used </h2>

- <b>Virtual Box</b>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
  <br />
First off we identify the network interfaces that can be used to capture network packet data: 
<br />
  
  <img src="https://i.imgur.com/mzv7wvV.png" height="80%" width="80%" alt="network interface identification"/>
<br />

   <b> so i used the "eth0" as the interface to capture network packet data from.
you can also use the "sudo tcpdump -D"  to identify the interface options available for packet capture


<br />


you can also use the "sudo tcpdump -D" and below is the output which shows the available interface options i have:  
<br />
<img src="https://i.imgur.com/vVBpbcS.png" height="80%" width="80%" alt="Data packet analysis"/>
<br />

<br />
the Captured packet data is sent into a file called capture.pcap using the "-w": <br/>
<br />
<img src="https://i.imgur.com/DsN4462.png" height="80%" width="80%" alt="Data packet analysis"/>
<br />
<br />
  <b> Brief explanations on the flags i used : 
  
     -nn: this specifies not to attempt to resolve IP addresses or ports to names.This is best practice from a security perspective, as the lookup data may not be valid. It also prevents malicious actors from being alerted to an investigation.
     
     -c9: Capture 9 packets of data and then exit where "C" stands for count, count 9 data packets.
     
     -port 80: I want to filter only port 80 traffic. This is the default HTTP port.
<br />
<br />
<br />

To verify that the captured data has been saved in the file we named capture.pcap, run ls -l capture.pcap : 
<br />
<img src="https://i.imgur.com/rmMFkWb.png" height="80%" width="80%" alt="Data packet analysis"/>
<br />

<br />
Now i used the tcpdump command to filter the packet header data from the capture.pcap capture file:  <br/>
<br />
<img src="https://i.imgur.com/cd9uKVo.png" height="80%" width="80%" alt="Data packet analysis"/>
<br />
<br />

 <b> 
 
     
      -r: this flag is to read the captured data from the named file.
      -v: this means verbose which displays the details of the data packet.

<br />

</p>

There are definitely lots of filters that can be used to analyse this data packet file depending on the case scenerio but just for the purposes of this project i chose to keep it simple and i hope it was helpful.

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
