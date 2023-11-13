# tcpdump-filter



Filtering: <br/>
Tcpdump also has a feature for filtering packets. With this feature I can capture only the traffic that I really want to analyze. I'll use filtering to capture DNS traffic to a specific DNS server. I will use the command:
 <br/> "sudo tcpdump -i eth0 -vn host 8.8.8.8 and port 53 &" 
 <br/>
 <br/> This command specifies that I only want packets where the source or destination IP address matches the address 8.8.8.8 and also specifies that I only want to see packets where the source or destination port matches port 53. 
 <br/>
  <img src="https://i.imgur.com/PKBmdUK.png" height="50%" width="50%"
  <br/>
  <br />
<br/>
To list all running jobs, I will use the command: "jobs -l"
 <br/>
<img src="https://i.imgur.com/dbqJBYl.png" height="60%" width="60%"
  <br/>
  <br />
<br/>
Now, I'll note down the job ID of the above process (637). <br/> 
 Next, I will execute a "dig" command: "dig @8.8.8.8 A example.com"
 <br/>
The dig command is a utility used to query a specific DNS server (in this case 8.8.8.8), 
 <br/> 
asking it for the A record for the specified domain (in this case "example.com").
<br/>
<img src="https://i.imgur.com/gsmAEhy.png" height="60%" width="60%"
  <br/>
 <img src="https://i.imgur.com/QHDqEOR.png" height="60%" width="60%" 
  <br/>
 <br/>
 <br/>
 Once that's done, I'll use the job ID that I noted down earlier to bring the process to foreground with the following command: fg % 637
 <br/>
<img src="https://i.imgur.com/9yYQmAI.png" height="60%" width="60%"
  <br/>
  <br/>
 <br/>
We see two captured packets, as our filter rules filtered out any other traffic.
 <br/>
<img src="https://i.imgur.com/zKA6moX.png" height="60%" width="60%"
  <br/>
<br/>
 <br/>
