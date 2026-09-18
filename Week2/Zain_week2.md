<img src="media/media/image1.png" style="width:5.80625in;height:1.75486in" />

1.  **<u>The OSI and TCP/IP layered models; the role of each layer; encapsulation:-</u>**

**OSI Model :-**

| **Layer** | **Layer Name** | **Main Role** | **Examples / Protocols** | **PDU** |
|:--:|:---|:---|:---|:---|
| **7** | Application | Provides network services directly to applications and users. | HTTP, HTTPS, FTP, DNS, SMTP | Data |
| **6** | Presentation | Handles data formatting, translation, encryption, and compression. | TLS/SSL, JPEG, ASCII, UTF-8 | Data |
| **5** | Session | Establishes, manages, and terminates communication sessions. | RPC, NetBIOS | Data |
| **4** | Transport | Provides end-to-end communication, reliability, flow control, and segmentation. | TCP, UDP | Segment / Datagram |
| **3** | Network | Handles logical addressing and routing between networks. | IP, ICMP, OSPF | Packet |
| **2** | Data Link | Provides node-to-node delivery, MAC addressing, and frame handling. | Ethernet, Wi-Fi, ARP | Frame |
| **1** | Physical | Transmits raw bits through cables, fiber, or radio signals. | Ethernet cables, Fiber, Wi-Fi signals | Bits |

**TCP/IP Model:-**

| **Layer** | **Layer Name** | **Main Role** | **Examples / Protocols** |
|:--:|:---|:---|:---|
| **4** | Application | Provides network services to applications. Combines OSI Layers 5–7. | HTTP, HTTPS, DNS, FTP, SMTP |
| **3** | Transport | Provides end-to-end communication and controls reliability and delivery. | TCP, UDP |
| **2** | Internet | Handles IP addressing and routing packets between networks. | IPv4, IPv6, ICMP |
| **1** | Network Access | Handles communication over the physical network, including frames and transmission. | Ethernet, Wi-Fi, ARP |

**Encapsulation:-**

| **Step** | **Layer** | **What Happens** | **Data Unit** |
|:--:|:---|:---|:---|
| 1 | Application | Application creates the data/message. | Data |
| 2 | Transport | TCP/UDP adds a header containing information such as ports. | Segment / Datagram |
| 3 | Network | IP adds source and destination IP addresses. | Packet |
| 4 | Data Link | Ethernet/Wi-Fi adds MAC addresses and creates a frame. | Frame |
| 5 | Physical | Frame is converted into electrical, optical, or radio signals. | Bits |

2.  **<u>IPv4 address structure; subnet masks and CIDR notation:-</u>**

**IPv4 address structure :-**

| **Topic** | **Easy Explanation** |
|:---|:---|
| **IPv4 Address Structure** | An IPv4 address is like a **unique address for a device on a network**. It has **32 bits** and is divided into **4 parts called octets**. |
| **Example** | 192.168.1.10 — each number is one octet. |
| **Octet Range** | Each part can contain a number from **0 to 255**. |
| **Network Part** | Tells us **which network** the device belongs to. |
| **Host Part** | Tells us **which device** is on that network. |
| **Simple Example** | In 192.168.1.10/24, 192.168.1 represents the network, while 10 identifies the device. |

### Subnet Masks :-

A **subnet mask** tells us which part of an IP address represents the **network** and which part represents the **device (host)**. It works together with the IP address to divide a network into smaller sections.

For example:192.168.1.10\
255.255.255.0 Here, 255.255.255 represents the **network part**, while 0 represents the **host part**.

Common subnet masks include:

- 255.0.0.0 → /8

- 255.255.0.0 → /16

- 255.255.255.0 → /24

- 255.255.255.128 → /25

- 255.255.255.192 → /26

### CIDR Notation :-

CIDR (Classless Inter-Domain Routing) is a short way of writing an IP address together with its subnet information. It uses a / followed by a number, such as /24.

**For example:**

192.168.1.0/24

Here, /24 means that the first 24 bits are used for the network, while the remaining 8 bits are available for hosts.

3.  **<u>Calculating networks and host counts; public and private address ranges:-</u>**

<img src="media/media/image2.png" style="width:5.76736in;height:2.11528in" />

It is divided into a network and host addresses. It identifies the subnet mask, usable IP range, network address, and broadcast address.

4.  **<u>Routing and switching concepts: Layer 2 vs Layer 3, the routing table:-</u>**

    **Routing and Switching Concepts:-**

- **Layer 2 Switching:**Uses MAC addresses to send data within the same network.

<!-- -->

- **Layer 3 Routing:**Uses IP addresses to send data between different networks.

<!-- -->

- **Routing Table:** A list of network routes that helps a router decide where to forward packets.

| **Destination Network** | **Subnet Mask** | **Next Hop**       | **Interface** |
|:------------------------|:----------------|:-------------------|:--------------|
| 192.168.1.0             | 255.255.255.0   | Directly Connected | eth0          |
| 192.168.2.0             | 255.255.255.0   | 192.168.1.1        | eth1          |
| 10.0.0.0                | 255.0.0.0       | 192.168.1.1        | eth1          |
| 0.0.0.0                 | 0.0.0.0         | 192.168.1.1        | eth1          |

<img src="media/media/image3.png" style="width:5.76667in;height:1.96667in" />

<img src="media/media/image4.png" style="width:5.76111in;height:1.61458in" />

1.  **<u>DNS resolution flow; common record types; querying with dig and nslookup:-</u>**

    <img src="media/media/image5.png" style="width:5.75764in;height:2.00347in" />

    This command asks the DNS system to find the IP address. It shows the answer along with some extra details like how long it took.

<img src="media/media/image6.png" style="width:3.875in;height:1.94792in" />

finds the IP address of a website name.

2.  **<u>Static routes, gateways, and inspecting routes from the command line:-</u>**

    <img src="media/media/image7.png" style="width:5.76319in;height:0.92153in" />

    It shows the list of routes your computer uses to send data. It tells you which gateway your internet traffic goes through to reach other networks.

    <img src="media/media/image8.png" style="width:5.76667in;height:0.68403in" />

    It s shows your default gateway

3.  **<u>HTTP request/response cycle and common status codes:-</u>**

    <img src="media/media/image9.png" style="width:5.28472in;height:2.31389in" />

It sends a request to a website and shows you everything that happens step by step.

<img src="media/media/image10.png" style="width:5.76111in;height:2.77431in" />

4.  **<u>TLS handshake; SSL certificate basics: chains, CAs, validity, and viewing a certificate:-</u>**

    <img src="media/media/image11.png" style="width:5.76389in;height:3.89931in" />

    It connects to a website securely and shows the details of its safety certificate — like who issued it, when it was made, and when it expires.

<img src="media/media/image12.png" style="width:5.76736in;height:3.94097in" />

<img src="media/media/image13.png" style="width:5.76736in;height:0.69375in" />

It picks out just the important parts of the certificate who it belongs to, who gave it out, and how long it stays valid.

**Practical:-**

<img src="media/media/image14.png" style="width:5.31042in;height:3.60625in" />

<img src="media/media/image15.png" style="width:5.76597in;height:1.51319in" />

I used dig to find the IP address of a website. Then I used curl -v to see how my computer talks to the website and gets a reply back. Finally, I used openssl to check the website's security certificate and see who made it and when it expires.

<img src="media/media/image16.png" style="width:5.76111in;height:1.31458in" />

1.  **<u>VLANs: access vs trunk ports, 802.1Q tagging, native VLAN:-</u>**

    **VLAN — 802.1Q:**

    <img src="media/media/image17.png" style="width:5.76111in;height:0.82639in" />

    It creates a VLAN interface with tag number 10 on top of your main network card .

    **Access vs Trunk Port :**

    <img src="media/media/image18.png" style="width:5.7625in;height:2.28333in" />

    **Native VLAN :**

    <img src="media/media/image19.png" style="width:3.69792in;height:1.25in" />

    It is used to delete that link.

2.  **<u>NAT concepts: source/destination NAT, port address translation:-</u>**

    <img src="media/media/image20.png" style="width:5.76667in;height:1.43542in" />

    It changes the private (internal) IP address of outgoing traffic to the public IP address, so your device can talk to the internet without exposing its real internal address.

    <img src="media/media/image21.png" style="width:5.76736in;height:0.92708in" />

    It takes incoming traffic on port 8080 and forwards it to a different internal device (192.168.1.100) on port 80.

**<u>3 .Diagnostic tools: ping, traceroute, ss, and netstat — interpreting results:-</u>**

<img src="media/media/image22.png" style="width:5.76181in;height:2.72778in" />

I checked ping and traceroute results to see connection speed and the path data takes to reach a website. I also looked at ss and netstat outputs to see which ports were open and which programs were using them.

**Practical Task: <u>Diagnose a simulated network fault using ping, traceroute, ss, and netstat; map the traffic flow through NAT :-</u>**

<img src="media/media/image23.png" style="width:5.76597in;height:1.54236in" />

It sends small test messages to a website and checks if it replies. It tells you if the connection is working and how fast it is.

<img src="media/media/image24.png" style="width:5.76458in;height:2.24653in" />

It helps you see where a connection might be slow or broken.

<img src="media/media/image25.png" style="width:5.76111in;height:1.27639in" />

It shows all the open network connections and ports on your computer. It tells you which services are listening and waiting for connections.

<img src="media/media/image26.png" style="width:5.76181in;height:2.07431in" />

It shows open ports and active connections, and additionally tells you which program is using each one.

<img src="media/media/image27.png" style="width:5.75833in;height:1.91944in" />

It shows NAT rules on system.

<img src="media/media/image28.png" style="width:5.76597in;height:1.51111in" />

1.  **<u>iptables tables and chains; rule structure and targets:-</u>**

    <img src="media/media/image29.png" style="width:5.52431in;height:2.13611in" />

It shows all the current firewall rules, organized into chains (INPUT, OUTPUT, FORWARD). It tells you what traffic is allowed or blocked and in what order.

<img src="media/media/image30.png" style="width:5.7625in;height:0.98819in" />

It adds a rule to the INPUT chain that allows incoming traffic on port 22 (SSH).

2.  **<u>The filter table and the nat table in practice:-</u>**

    <img src="media/media/image31.png" style="width:5.76389in;height:1.45139in" />

<img src="media/media/image32.png" style="width:5.76319in;height:1.98819in" />

filter table controls "allow/block" decisions, while nat table controls "address translation" decisions.

<img src="media/media/image33.png" style="width:5.76597in;height:1.09514in" />

It adds another rule that allows incoming traffic on port 443 (HTTPS), so people can securely browse websites hosted on this machine.

<img src="media/media/image34.png" style="width:5.76597in;height:1.1875in" />

It adds a final rule at the end of the INPUT chain that blocks (drops) everything else that wasn't already allowed.

<img src="media/media/image35.png" style="width:5.75764in;height:1.35972in" />

3.  **<u>Simplified rules with ufw; zone-based control with firewalld:-</u>**

    <img src="media/media/image36.png" style="width:2.94792in;height:0.84375in" />

    This is used to Allow port 443 through ufw command.

    <img src="media/media/image37.png" style="width:5.11458in;height:2.44792in" />

    It block All incomming traffic and Allow all outgoing .

    UfW enable It is used to activate firewall .

    <img src="media/media/image38.png" style="width:4.98403in;height:2.20486in" />

    **Firewalld :-**

    <img src="media/media/image39.png" style="width:5.76597in;height:2.79167in" />

    Firewall d use the zones and every zone has its own rules according to network type.

4.  **<u>Application confinement with AppArmor:-</u>**

    <img src="media/media/image40.png" style="width:4.92708in;height:2.37361in" />

It shows whether AppArmor is running and lists which applications currently have security profiles .

**Practical Task: <u>Write iptables rules to allow only SSH and HTTPS inbound, block all else, and verify with ss; then replicate with ufw</u>**

<img src="media/media/image41.png" style="width:5.75833in;height:2.37639in" />

<img src="media/media/image42.png" style="width:5.04722in;height:3.88889in" />

I wrote iptables rules to allow only SSH and HTTPS traffic and block everything else.then , I recreated the same setup using ufw which does the same job with simpler commands.

<img src="media/media/image43.png" style="width:5.76667in;height:1.49375in" />

1.  **<u>Capturing traffic with Wireshark and tcpdump:-</u>**

    **<u>Wireshark :-</u>**

    <img src="media/media/image44.png" style="width:5.76389in;height:2.52014in" />

It shows network traffic captured in Wireshark. It displays packets with their source, destination, protocol, and other details, allowing us to analyze the communication.

**<u>TCPDUMP:-</u>**

<img src="media/media/image45.png" style="width:5.75694in;height:2.16667in" />

It shows network packets captured using tcpdump. The terminal output displays packet details such as source and destination IPs, ports, flags, and packet length.

2.  **<u>Applying capture and display filters:-</u>**

**Wireshark:-**

<img src="media/media/image46.png" style="width:5.76667in;height:1.07153in" />

<img src="media/media/image47.png" style="width:5.76597in;height:0.92083in" />

<img src="media/media/image48.png" style="width:5.76389in;height:0.93125in" />

It shows captured network traffic filtered by different protocols such as **TLS, DNS, and TCP.**

**TCP DUMP:-**

<img src="media/media/image49.png" style="width:5.75972in;height:0.82014in" />

<img src="media/media/image50.png" style="width:5.76181in;height:1.21944in" />

It shows packet capture from the terminal using tcpdump, including DNS queries, source and destination IPs, ports, and packet details.

3.  **<u>Command-line capture workflows with tcpdump for remote/headless hosts:-</u>**

    <img src="media/media/image51.png" style="width:5.50972in;height:1.76458in" />

It shows live network traffic captured using tcpdump on the eth0 interface. It displays the source and destination IP addresses, ports, TCP flags, and packet details.

**Practical Tasks:-**

<img src="media/media/image44.png" style="width:5.76389in;height:2.52014in" />

<img src="media/media/image52.png" style="width:5.76597in;height:1.06181in" />

<img src="media/media/image53.png" style="width:5.76181in;height:0.74583in" />
