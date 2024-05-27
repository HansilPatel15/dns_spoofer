<h1>dns_spoofer</h1>


<h2>Description</h2>
- dns spoofer script <br>
<br>This script intercepts and modifies DNS requests to perform DNS spoofing, redirecting requests for specific domains to a specified IP address. It uses the netfilterqueue and Scapy libraries to capture and manipulate packets.<br>

<br>Features: <br>
- DNS Interception: Captures DNS requests using netfilterqueue and iptables.<br>
- DNS Spoofing: Modifies DNS responses to redirect traffic for specific domains.<br>
- Packet Manipulation: Updates necessary fields and recalculates checksums to ensure packet validity.<br>
<br />


<h2>Languages and Utilities Used</h2>

- <b>Python</b> 


<h2>Environments Used </h2>

- <b>Linux</b> 

<h2>Usage: </h2>
 Run the script with the required options:
<br>sudo python dns_spoof.py
<br>Set up iptables rules:
<br>sudo iptables -I FORWARD -j NFQUEUE --queue-num 0
<br>sudo iptables -I INPUT -j NFQUEUE --queue-num 0
<br>sudo iptables -I OUTPUT -j NFQUEUE --queue-num 0

<br><b> Example: </b>
<br>
The script is configured to spoof DNS requests for "www.bing.com" and redirect them to the IP address "10.0.2.15". Modify the domain and IP address as needed in the process_packet function.
<br>
<b>Requirements:</b><br>
- Python 3.x<br>
- Scapy library (pip install scapy)
- NetfilterQueue library (pip install NetfilterQueue)<br>
- Root or sudo privileges for packet manipulation<br>
