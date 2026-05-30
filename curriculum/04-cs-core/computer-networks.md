# Computer Networks

Networks questions are common in **Wipro, Cognizant, Accenture, Tech Mahindra**. Heavier in **Infosys SP/DSE technical**. Focus on OSI/TCP-IP, protocols, and a few subnetting basics.

## Concept tree

1. **Networking basics** — what a network is, LAN/MAN/WAN/PAN.
2. **Network topologies** — bus, star, ring, mesh, tree, hybrid.
3. **OSI 7-layer model** + **TCP/IP 4-layer model**.
4. **Devices** — repeater, hub, bridge, switch, router, gateway.
5. **Physical & data link layer** — framing, error detection (parity, checksum, CRC), MAC addresses, ARP, switching.
6. **Network layer** — IP addressing (IPv4/IPv6), subnetting, routing (static, RIP, OSPF — concept), ICMP.
7. **Transport layer** — TCP vs UDP, ports, 3-way handshake, congestion / flow control, sliding window.
8. **Session / Presentation / Application layers** — DNS, HTTP/HTTPS, FTP, SMTP, POP3, IMAP, DHCP, TLS/SSL.
9. **Web & security basics** — symmetric vs asymmetric encryption, public-key infrastructure, hashing, digital signatures.
10. **Wireless basics** — Wi-Fi standards, bluetooth (lightweight awareness).
11. **Common attacks** — DDoS, MITM, phishing, SQL injection, XSS (just be aware).

## Must-know definitions

- **IP address**: a logical address (e.g., 192.168.1.10). IPv4 is 32-bit, IPv6 is 128-bit.
- **MAC address**: a physical 48-bit hardware address burned into the NIC.
- **DNS**: maps human-readable domain names → IP addresses.
- **DHCP**: protocol for automatically assigning IPs to devices on a LAN.
- **TCP**: connection-oriented, reliable, ordered.
- **UDP**: connectionless, unreliable, fast.
- **HTTP**: stateless application-layer protocol for the web; HTTPS = HTTP over TLS.
- **TLS/SSL**: cryptographic protocol securing HTTP, SMTP, etc.
- **Subnet mask**: separates network and host portions of an IP.

## Top 30 interview questions with model answers

**1. What is the OSI model? Why was it created?**
A 7-layer conceptual framework for network communication: Physical, Data Link, Network, Transport, Session, Presentation, Application. It standardises functions so that products from different vendors interoperate.

**2. Layers of OSI and their job (memorise mnemonic):**
*All People Seem To Need Data Processing* — bottom up: Physical (bits), Data Link (frames + MAC), Network (packets + IP + routing), Transport (segments + TCP/UDP), Session (dialog control), Presentation (encryption, encoding, compression), Application (HTTP, DNS, FTP, SMTP).

**3. OSI vs TCP/IP model?**
TCP/IP has 4 layers: Network Access (= OSI 1+2), Internet (= OSI 3), Transport (= OSI 4), Application (= OSI 5+6+7). TCP/IP is what the internet actually uses.

**4. Connection-oriented vs connectionless?**
Connection-oriented (TCP) establishes a session before data transfer (handshake) and guarantees delivery. Connectionless (UDP) sends packets independently with no setup or guarantee.

**5. TCP vs UDP?**
| Feature             | TCP                         | UDP                       |
| ------------------- | --------------------------- | ------------------------- |
| Connection          | Yes (3-way handshake)       | No                        |
| Reliability         | Yes (ACK, retransmit)       | No                        |
| Ordering            | Yes                         | No                        |
| Speed               | Slower                      | Faster                    |
| Header size         | 20-60 bytes                 | 8 bytes                   |
| Use cases           | HTTP, FTP, SMTP, SSH        | DNS, VoIP, video stream   |

**6. Explain TCP 3-way handshake.**
1. Client → Server: SYN (seq=x).
2. Server → Client: SYN-ACK (seq=y, ack=x+1).
3. Client → Server: ACK (ack=y+1).
After this, the connection is established and data can flow.

**7. Explain TCP 4-way termination.**
- Side A: FIN
- Side B: ACK
- Side B: FIN
- Side A: ACK
Both half-closes ensure data in transit is delivered cleanly.

**8. What is the difference between flow control and congestion control?**
- *Flow control* (TCP sliding window) prevents the sender from overwhelming a slow receiver.
- *Congestion control* (slow start, congestion avoidance, fast retransmit, fast recovery) prevents the network from being overwhelmed.

**9. What is a port number?**
A 16-bit integer (0-65535) identifying a process on a host. Well-known ports: 22 (SSH), 25 (SMTP), 53 (DNS), 80 (HTTP), 110 (POP3), 143 (IMAP), 443 (HTTPS), 3306 (MySQL).

**10. What is DNS? How does resolution work?**
DNS maps domain names to IP addresses. Resolution: client asks local resolver → root server → TLD server (.com) → authoritative server → returns IP, which is then cached.

**11. What happens when you type a URL in a browser?** (super-classic)
1. Browser checks cache for DNS → if not, resolves via DNS.
2. TCP connection (3-way handshake) to server's IP on port 80/443.
3. TLS handshake (if HTTPS) to negotiate encryption.
4. Browser sends HTTP GET request.
5. Server returns HTTP response (HTML, JSON, etc.) with status code.
6. Browser parses HTML, fetches CSS/JS/images (more requests).
7. Renders DOM, executes JS, displays page.
8. TCP connection closes (or stays open with keep-alive).

**12. IPv4 vs IPv6?**
IPv4 is 32-bit (~4.3 billion addresses), IPv6 is 128-bit (~3.4 × 10³⁸). IPv6 uses colon-hex notation, has built-in IPSec support, no broadcast (only multicast), and simpler header.

**13. What is subnetting?**
Dividing a large network into smaller subnetworks by extending the network portion of the IP using a custom subnet mask. Reduces broadcast domain size and improves security/routing.

**14. Public vs private IP?**
Public IPs are routable on the internet. Private ranges (RFC 1918): 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16 — only usable within a LAN, translated via NAT.

**15. What is NAT?**
Network Address Translation — a router rewrites private source IPs to a public IP (and back) so multiple devices share one public IP.

**16. Difference between router, switch, and hub?**
- **Hub**: layer 1; broadcasts to all ports.
- **Switch**: layer 2; uses MAC table to forward to specific ports.
- **Router**: layer 3; forwards between networks using IP and routing tables.

**17. What is ARP?**
Address Resolution Protocol — maps a known IPv4 address on a LAN to a MAC address. Devices broadcast "who has 192.168.1.5?" and the owner replies.

**18. What is ICMP?**
Internet Control Message Protocol — used for diagnostics (ping, traceroute) and error reporting (host unreachable, TTL exceeded).

**19. HTTP vs HTTPS?**
HTTPS = HTTP over TLS. Provides encryption, authentication (via certificates), and integrity. HTTP runs on 80, HTTPS on 443.

**20. HTTP methods?**
GET (retrieve), POST (create), PUT (replace), PATCH (partial update), DELETE (remove), HEAD (metadata only), OPTIONS (capabilities).

**21. HTTP status code classes?**
1xx informational, 2xx success (200 OK, 201 Created), 3xx redirection (301, 302, 304), 4xx client error (400, 401, 403, 404, 429), 5xx server error (500, 502, 503).

**22. Symmetric vs asymmetric encryption?**
Symmetric: same key for encrypt/decrypt (AES). Fast, but key distribution is hard.
Asymmetric: public/private key pair (RSA, ECC). Slower, used to exchange a session symmetric key. TLS uses asymmetric to set up, symmetric to transfer.

**23. What is hashing? Examples.**
A one-way function mapping data to fixed-length output (MD5, SHA-1, SHA-256). Used for integrity checks and password storage (with salt). Hashes are *not* reversible.

**24. What is a digital signature?**
Sign = hash(message) encrypted with sender's private key. Verify = decrypt with sender's public key, compare to fresh hash. Provides integrity + authenticity + non-repudiation.

**25. What is a firewall?**
A device or software that filters incoming/outgoing traffic by rules (IP, port, protocol). Can be stateful (tracks connections) or stateless.

**26. What is a VPN?**
Virtual Private Network — encrypts traffic between a client and a gateway, making the client appear on the remote network.

**27. Difference between cookie and session?**
A cookie is data stored on the client; a session is server-side state identified by a session ID (often stored in a cookie). Cookies travel with every request.

**28. What is DHCP and its DORA process?**
Dynamic Host Configuration Protocol assigns IPs automatically. Process: Discover, Offer, Request, Acknowledge (DORA).

**29. What is a CDN?**
Content Delivery Network — geographically distributed servers caching content close to users for low latency and high availability.

**30. What is the difference between latency and bandwidth?**
- **Latency**: time to send a single packet (in ms).
- **Bandwidth**: amount of data per second (Mbps/Gbps).
A network can be high-bandwidth but high-latency (e.g., satellite).

## Subnetting quick reference

```
/8   = 255.0.0.0       = 16,777,214 hosts
/16  = 255.255.0.0     = 65,534 hosts
/24  = 255.255.255.0   = 254 hosts
/25  = 255.255.255.128 = 126 hosts
/26  = 255.255.255.192 = 62 hosts
/27  = 255.255.255.224 = 30 hosts
/28  = 255.255.255.240 = 14 hosts
/29  = 255.255.255.248 = 6 hosts
/30  = 255.255.255.252 = 2 hosts
```

Formula: usable hosts = 2^(32-prefix) − 2.

Practice: given `192.168.10.0/26`, how many subnets and hosts?

## Diagrams you should be able to draw

- OSI vs TCP/IP layer mapping.
- TCP 3-way handshake.
- HTTPS handshake (high level).
- DNS resolution chain.
- ARP request/reply.

## Quick revision card

- OSI: PDNTSPA (Physical, Data Link, Network, Transport, Session, Presentation, Application).
- TCP = reliable, ordered, handshake; UDP = fast, no guarantee.
- 3-way handshake: SYN → SYN-ACK → ACK.
- Ports to remember: 22, 25, 53, 80, 110, 143, 443.
- DNS: name → IP, recursive resolution with caching.
- Subnet mask separates net + host portions.
- HTTPS = HTTP + TLS; symmetric+asymmetric crypto combined.
- Status codes: 200, 301, 401, 403, 404, 500.
- Layer-2 device = switch, Layer-3 = router.
- DORA = Discover, Offer, Request, Ack.
