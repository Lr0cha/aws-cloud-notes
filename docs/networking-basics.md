<div align="center">
  <h1>📡 Network Basic Essentials  </h1>
</div>

A network typically involves three parts:

1. Two or more devices that **communicate** with each other. 
2. A communication **channel** between the devices: 
   - Electrical (metallic) cable, optical (fiber optic) cable, or wireless. 
3. Communication standard **protocols**.

> [!NOTE]\
> **Computer networks** are the sharing of information and resources.

---

## OSI Model (Open Systems Interconnection)

- The OSI Model consists of **7 layers**, each with specific functions and responsibilities. 
- This layered approach makes it easier for **different** devices and technologies to **work together**. 
- The OSI model provides a **clear structure** for data transmission and managing network issues.

### OSI Layers

1. **Physical Layer** 
   Function: Transmits raw **binary** data over **physical** media. 
   Examples: Ethernet cables, hubs, radio waves. 

2. **Data Link Layer** 
   Function: Provides node-to-node data transfer, **framing**, and error detection. 
   Examples: MAC address, switches, ARP.

3. **Network Layer** 
   Function: Handles logical **addressing** and **routing** of **packets**. 
   Examples: IP, ICMP, routers. 

4. **Transport Layer** 
   Function: Ensures reliable (or best-effort) **delivery between devices**. 
   Examples: TCP (reliable), UDP (unreliable). 

5. **Session Layer** 
   Function: Manages sessions/connections between applications. 
   Examples: NetBIOS, RPC. 

6. **Presentation Layer** 
   Function: Translates, encrypts, or compresses data for the application layer. 
   Examples: SSL/TLS, JPEG, ASCII, MPEG. 

7. **Application Layer** 
   Function: Closest to the end-user, provides **network services**. 
   Examples: HTTP, SMTP, FTP, DNS. 

> [!IMPORTANT]\
> The OSI model is a **conceptual** framework, while the [TCP/IP](https://www.geeksforgeeks.org/computer-networks/tcp-ip-model/) model is a real-world framework. The TCP/IP model directly maps to practical implementations like the internet and modern networks.
---

### 📹 Example: Video Call (Person A → Person B)

- **Application Layer**: Person A uses an application like Zoom or Microsoft Teams to initiate a video call. 
- **Presentation Layer**: The video and audio streams are compressed and encrypted for transmission. 
- **Session Layer**: A session is established between Person A and Person B to maintain the video call. 
- **Transport Layer**: Data is divided into packets with sequence numbers and error checking (e.g., TCP or UDP depending on the application’s needs). 
- **Network Layer**: Packets are addressed with IP addresses and routed through different networks. 
- **Data Link Layer**: Frames are created, containing the MAC addresses for local delivery and error detection. 
- **Physical Layer**: Data is transmitted as electrical signals (on a cable) or radio waves (over Wi-Fi). 

> [!NOTE]\
> On the receiver’s side (Person B), this process is reversed and the video call is reassembled and displayed on their screen.
---

## 🔢 IP Addressing & Subnetting
> [!IMPORTANT]\
> IP = Internet Protocol, set of rules, for routing and addressing **packets** of data so they can travel **across networks** and arrive at the **correct destination**.

- **IPv4 Format:** `xxx.xxx.xxx.xxx` (0–255 range) 
- **IPv6: Newer** format to replace IPv4 (e.g., `2001:db8::1`) 

**Subnetting** 
- Divides local networks into **smaller segments**. 
- **Subnet Mask:** Defines network and host **parts** (e.g., `255.255.255.0`) 
- **CIDR Notation:** `/24` means 256 IPs from `.0` to `.255` 

**Example:** 
- IP: `192.168.10.14` 
- Subnet Mask: `255.255.255.0` 
- Network: `192.168.10.0` 
- Host Range: `192.168.10.1 – 192.168.10.254` 

---

## 🏠 Public vs Private IP Addresses

<div align="center">
  
| Type    | Description          | Example Ranges                            |
|---------|----------------------|-------------------------------------------|
| Private | Local networks only  | 10.0.0.0/8, 192.168.0.0/16, 172.16.0.0/12 |
| Public  | Globally routable    | Assigned by ISP via IGW                   |

</div>

> [!IMPORTANT]\
> **NAT (Network Address Translation):** Allows private IPs to **share** a public IP. 

---

## 🌐 Protocols

Protocols are the rules for communication between devices. 
They **define** what, how, and when data is transmitted.

- **Communication Protocols**: HTTP, TCP, UDP, ARP, IP, DHCP 
- **Management Protocols**: FTP 
- **Security Protocols**: SSL/TLS, HTTPS 

---

## ⚔️ TCP vs UDP

<div align="center">
  
| Feature       | TCP (Connection-oriented) | UDP (Connectionless)       |
|---------------|----------------------------|---------------------------|
| Reliability   | Reliable (ACKs, retransmits) | Unreliable, best-effort |
| Speed         | Slower                     | Faster |
| Use Cases     | Web, email, file transfer  | Streaming, VoIP, DNS |
| Examples      | HTTP, HTTPS, SMTP, FTP     | DNS, DHCP, VoIP |

</div>

---

## 🌐 Ports and Protocols (Examples)
Ports are virtual places within an operating system where network connections start and end.

> [!NOTE]\
> Help computers **sort** the network traffic they receive.

<div align="center">
  
| Protocol | Port | Use Case                         |
|----------|------|----------------------------------|
| HTTP     | 80   | Insecure web traffic             |
| HTTPS    | 443  | Secure web traffic (SSL/TLS)     |
| FTP      | 21   | File transfer                    |
| SSH      | 22   | Secure remote access             |
| DNS      | 53   | Domain resolution                |
| SMTP     | 25   | Sending emails                   |
| POP3     | 110  | Email retrieval (download)       |

</div>

---

## 🔥 Firewalls

**Filter** traffic based on rules: 
- By IP address;
- By port number;
- By protocol type; 

> [!NOTE]\
> Can be **hardware (routers)** or **software (iptables, firewalld, ufw)**. 

---

## 🔐 VPN (Virtual Private Network)

- Creates **"encrypted tunnels"** over public networks. 
- Uses: Privacy, remote access, bypass restrictions. 
- Protocols: OpenVPN, IPSec, WireGuard. 

---

## Proxy Servers

Acts as intermediary between client and server. 
- **Forward Proxy**: Controls outbound access. 
- **Reverse Proxy**: Balances/caches inbound traffic. 

Use Cases: Anonymity, performance, filtering content. 

---

## Basic Linux Networking CLI

- `ip a` – Show IP addresses and interfaces;
- `ip r` – Show gateway default;
- `ip link` – Show/manage interfaces;
- `nslookup domain.com` – Query DNS;
- `ping domain.com` – Check host reachability ;
- `traceroute domain.com` – Show path to host; 
- `curl ifconfig.me` – Show external IP ;
- `wget https://example.com` – Test HTTP/HTTPS reachability;
- `ip route` – View routing table;
- `ss -tuln` – Show listening ports.

---


## 🔗 Interesting resources
- [What is OSI Model? - Layers of OSI Model](https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/)
- [TCP/IP model](https://www.geeksforgeeks.org/computer-networks/tcp-ip-model/)
- [Difference between Private and Public IP addresses](https://www.geeksforgeeks.org/computer-networks/difference-between-private-and-public-ip-addresses/)
- [What is a computer port? ](https://www.cloudflare.com/learning/network-layer/what-is-a-computer-port/)
- [How networks work](https://mkdev.me/posts/how-networks-work-what-is-a-switch-router-dns-dhcp-nat-vpn-and-a-dozen-of-other-useful-things)

<div align="center">
  <a href="..">◀️</a> |
  <a href="./01-cloud-overview.md">▶️</a>
</div>
