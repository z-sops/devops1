Exploring OSI and TCP/IP Models: Layers, Protocols, and DevOps Applications

zeeshan baig's photo
zeeshan baig
·
May 13, 2025
·
19 min read

Table of contents
OSI Model: A 7-Layer Framework
Layer Breakdown
Layer Breakdown
TCP/IP Model: A Practical 4-Layer Model
Layer Breakdown
OSI vs. TCP/IP Mapping
Layer Breakdown
OSI vs. TCP/IP Mapping
Real-World Example: Sending an Email
Diagram: OSI and TCP/IP Data Flow
Diagram: OSI and TCP/IP Data Flow
Key Protocols and Ports for DevOps
DevOps Relevance
DevOps Relevance
Launching an Ubuntu EC2 Instance and Securing It with Security Groups (Using Nginx)
What Are AWS EC2, Ubuntu, Security Groups, and Nginx?
Prerequisites
Step-by-Step Guide: Launch an Ubuntu EC2 Instance and Configure Security Groups
Step 1: Launch a Free-Tier Ubuntu EC2 Instance
Step 2: Understand Security Groups
Step 3: Create a Security Group
Step 4: Configure Outbound Rules
Step 5: Save and Attach the Security Group
Step 6: Understanding Web Servers and Why Nginx Is Used
Step 7: Install and Test Nginx
Step 8: Test SSH Connectivity
Why Security Groups Are Essential
Best Practices for Security Groups
Example Security Group Rules
Conclusion
Hands-On Networking Commands for Cloud Troubleshooting
Understanding ICMP (Internet Control Message Protocol)
Networking Commands Cheat Sheet
🟢 ping
🧭 traceroute (Linux/macOS) / tracert (Windows)
📊 netstat
🌐 curl
🔍 dig
🔎 nslookup
Tips for Effective Use
Conclusion

Show more
Lets dives into the OSI and TCP/IP network models, breaking down their layers with practical examples, illustrating data flow through a real-world scenario, and highlighting key protocols used in DevOps workflows.

OSI Model: A 7-Layer Framework
The OSI (Open Systems Interconnection) model is a theoretical framework that organizes network functions into seven distinct layers, each handling a specific task in data communication.

Layer	Name	Function Overview	Protocols/Technologies
7	Application	User-facing services for apps	HTTP, HTTPS, FTP, DNS, SMTP
6	Presentation	Data formatting, encryption	SSL/TLS, PNG, ASCII
5	Session	Session setup and management	NetBIOS, L2TP
4	Transport	Reliable data delivery	TCP, UDP
3	Network	Packet routing and addressing	IP, ICMP, RIP
2	Data Link	Local network data transfer	Ethernet, Wi-Fi, ARP
1	Physical	Physical signal transmission	Cables, Wi-Fi, USB
Layer Breakdown
Application Layer:

Role: Provides network access to user applications (e.g., web browsers, email clients).

Example: When you visit a website, HTTP sends your request to the server.

Data: Messages (e.g., webpage data).

Presentation Layer:

Role: Converts data into a standard format, handles encryption, and compresses data.

Example: TLS encrypts your credit card details during online shopping.

Data: Encoded or formatted data (e.g., encrypted text).

Session Layer:

Role: Establishes and maintains communication sessions between devices.

Example: Keeps your video call connected without re-authenticating.

Data: Session context (e.g., login state).

Transport Layer:

Role: Manages end-to-end data transfer, ensuring reliability or speed.

Example: TCP ensures all email data arrives correctly, while UDP streams video quickly.

Data: Segments (e.g., data chunks).

Network Layer:

Role: Routes data packets across networks using logical addresses (IP).

Example: IP directs your Google search request to Google’s servers.

Data: Packets (e.g., IP packets).

Data Link Layer:

Role: Ensures error-free data transfer within a local network using physical addresses (MAC).

Example: Ethernet delivers data between your laptop and router.

Data: Frames (e.g., Ethernet frames).

Physical Layer:

Role: Transmits raw bits over physical media like cables or Wi-Fi.

Example: Fiber optic cables carry your internet data as light pulses.

Data: Bits (e.g., 0s and 1s).

TCP/IP Model: A Practical 4-Layer Model
The TCP/IP model is a streamlined, real-world framework used in modern networks, including the internet, with fewer layers than OSI.

Layer	Function Overview	Protocols/Technologies
Application	User services, formatting, sessions	HTTP, HTTPS, FTP, DNS, SMTP
Transport	End-to-end data delivery	TCP, UDP
Internet	Packet routing and addressing	IP, ICMP
Network Access	Local transfer and physical signaling	Ethernet, Wi-Fi, ARP
Layer Breakdown
Application Layer:

Role: Combines OSI’s Application, Presentation, and Session layers, handling user interactions, data formatting, and session management.

Example: HTTPS serves a secure webpage, TLS encrypts it, and session management keeps you logged in.

Data: Messages.

Transport Layer:

Role: Manages data delivery, with TCP for reliability or UDP for speed.

Example: TCP ensures a file download is complete, UDP supports live gaming.

Data: Segments.

Internet Layer:

Role: Routes packets across networks using IP addresses.

Example: IP sends your video stream packets to the correct server.

Data: Packets.

Network Access Layer:

Role: Combines OSI’s Data Link and Physical layers, handling local data transfer and physical transmission.

Example: Wi-Fi transmits data frames from your device to the router.

Data: Frames and bits.

OSI vs. TCP/IP Mapping
OSI Application, Presentation, Session → TCP/IP Application

OSI Transport → TCP/IP Transport

OSI Network → TCP/IP Internet

OSI Data Link, Physical → TCP/IP Network Access

Real-World Example: Sending an Email
When you send an email using a client like Gmail:

Application Layer (OSI 7/TCP/IP Application): SMTP (port 587) formats and sends the email.

Presentation Layer (OSI 6): TLS encrypts the email for security.

Session Layer (OSI 5): Maintains the connection to the mail server.

Transport Layer (OSI 4/TCP/IP Transport): TCP (port 587) ensures all email data is delivered.

Network Layer (OSI 3/TCP/IP Internet): IP routes the packets to the mail server.

Data Link Layer (OSI 2/TCP/IP Network Access): Ethernet transfers data within your local network.

Physical Layer (OSI 1/TCP/IP Network Access): Data travels over Wi-Fi or cables.

Diagram: OSI and TCP/IP Data Flow

Copy

Copy
OSI Model                        TCP/IP Model
+---------------------+         +---------------------+
| 7. Application      |<------->| Application         |
|    (HTTP, SMTP)     |         | (HTTP, SMTP, DNS)   |
+---------------------+         +---------------------+
| 6. Presentation     |         |                     |
|    (TLS)            |         |                     |
+---------------------+         |                     |
| 5. Session          |         |                     |
+---------------------+         +---------------------+
| 4. Transport        |<------->| Transport           |
|    (TCP, UDP)       |         | (TCP, UDP)          |
+---------------------+         +---------------------+
| 3. Network          |<------->| Internet            |
|    (IP)             |         | (IP, ICMP)          |
+---------------------+         +---------------------+
| 2. Data Link        |<------->| Network Access      |
|    (Ethernet)       |         | (Ethernet, Wi-Fi)   |
+---------------------+         |                     |
| 1. Physical         |         |                     |
|    (Cables, Wi-Fi)  |         |                     |
+---------------------+         +---------------------+
Data Flow:

Sender: Data starts at the Application layer, is formatted, segmented, and encapsulated as it moves down to the Physical layer for transmission.

Network: Routers (Network layer), switches (Data Link layer), and cables (Physical layer) process and forward the data.

Receiver: Data moves up from the Physical layer, with each layer removing headers until the original message reaches the Application layer.

Key Protocols and Ports for DevOps
These protocols are essential for network communication and play critical roles in DevOps tasks like deployment, monitoring, and automation.

Protocol	Port(s)	Role	DevOps Use Case
HTTP	80	Transfers webpage data	Hosts internal tools, serves CI/CD artifacts
HTTPS	443	Secure webpage data with TLS	Secure API calls, cloud deployments
SSH	22	Secure remote server access	Server config, Git operations, deployments
FTP	20, 21	File transfers (unsecure)	Legacy systems, rarely used in DevOps
SFTP	22	Secure file transfers over SSH	Secure log transfers, backup automation
SMTP	25, 587	Sends emails	Automated alerts in CI/CD pipelines
DNS	53	Resolves domain names to IPs	Service discovery, microservices routing
DevOps Relevance
SSH (Port 22): Enables secure server access for tasks like updating configurations (e.g., ssh user@server) or deploying code.

DNS (Port 53): Resolves service names (e.g., db.example.com) in cloud environments, critical for Kubernetes or AWS.

HTTPS (Port 443): Secures communication for CI/CD tools accessing repositories or cloud APIs.

SMTP (Port 587): Sends automated alerts (e.g., pipeline failures) to DevOps teams.

SFTP (Port 22): Safely transfers configuration files or logs during automation.

HTTP (Port 80): Used for non-secure dev environments or internal dashboards.

FTP (Ports 20, 21): Mostly obsolete in DevOps, replaced by SFTP or cloud storage.

Launching an Ubuntu EC2 Instance and Securing It with Security Groups (Using Nginx)
This guide demonstrates launching an AWS EC2 instance with Ubuntu 20.04 LTS, configuring Security Groups to secure it, and setting up an Nginx web server to test network access. Designed for DevOps beginners, it connects to OSI/TCP/IP concepts (e.g., SSH, HTTP protocols) and explains why Nginx is used to validate Security Group rules. Using the AWS Free Tier, you’ll build a secure web server with minimal local storage impact, addressing past concerns about limited disk space.

What Are AWS EC2, Ubuntu, Security Groups, and Nginx?
Amazon EC2 (Elastic Compute Cloud) offers virtual servers for hosting applications, with the AWS Free Tier providing 750 hours/month of a t2.micro instance for learning.

Ubuntu 20.04 LTS is a stable, widely-used Linux distribution, ideal for EC2 instances running web servers or DevOps tools.

Security Groups are virtual firewalls controlling EC2 instance traffic at the OSI model’s Network (IP) and Transport (port) layers, aligning with TCP/IP’s Internet and Transport layers. Rules specify protocol (e.g., TCP), port (e.g., 80 for HTTP), and source/destination (e.g., IP address). They’re stateful, auto-allowing responses for permitted inbound traffic.

Nginx is a high-performance web server handling HTTP/HTTPS requests, used here to test Security Group rules. It’s lightweight, supports high concurrency, and is a modern alternative to Apache.

Networking Context: This guide uses SSH (port 22) and HTTP (port 80), Application-layer protocols from your OSI/TCP/IP studies, to test Security Group functionality.

Prerequisites
An AWS Free Tier account (aws.amazon.com/free).

A terminal (e.g., Terminal on macOS) for SSH.

Basic OSI/TCP/IP knowledge (ports, protocols).

A minimal directory (e.g., ~/aws-keys/) for key pairs to save disk space.

Step-by-Step Guide: Launch an Ubuntu EC2 Instance and Configure Security Groups
Step 1: Launch a Free-Tier Ubuntu EC2 Instance
Launch a t2.micro instance with Ubuntu 20.04 LTS.

Sign In to AWS:

Open the AWS Management Console and log in.
Navigate to EC2:

Click “Services” → “EC2” → “Instances” → “Launch instances”.
Configure the Instance:

Name: “UbuntuNginxServer”.

AMI: Search “Ubuntu” and select “Ubuntu Server 20.04 LTS (HVM), SSD Volume Type” (free-tier eligible, 64-bit x86).

Instance Type: “t2.micro” (free-tier eligible).

Key Pair:

Click “Create new key pair”, name it “nginx-key”, select “.pem”, and download (nginx-key.pem).

Save in ~/aws-keys/ and set permissions:


Copy

Copy
  chmod 400 ~/aws-keys/nginx-key.pem
Network Settings:

Use default VPC and subnet.

Under “Firewall (security groups)”, select “Create security group” and enable “Allow SSH traffic” (port 22). We’ll customize later.

Storage: Keep 8GB gp3 root volume (free-tier eligible).

Launch: Click “Launch instance”. Wait 2-3 minutes for “Running” status.

Note Public IP:

Select “UbuntuNginxServer” and copy the “Public IPv4 address” (e.g., 54.123.45.67).
Storage Tip: Store only the key pair (~1KB) to avoid disk space issues on your MacBook.

Step 2: Understand Security Groups
Security Groups filter traffic to/from your EC2 instance, like firewalls in the TCP/IP model.

Features:

Inbound Rules: Allow incoming traffic (e.g., HTTP on port 80).

Outbound Rules: Allow outgoing traffic (default: all).

Stateful: Permitted inbound traffic (e.g., HTTP request) allows its response (e.g., webpage) automatically.

Parameters: Protocol (TCP), port (80), source (e.g., 0.0.0.0/0).

Example: For a web server, allow:

SSH (port 22, TCP) from your IP for management.

HTTP (port 80, TCP) from anywhere for public access.

Why Critical: Security Groups block unauthorized access, ensuring only intended traffic (e.g., HTTP, SSH) reaches the instance.

Step 3: Create a Security Group
Create a Security Group for the Nginx web server.

Access Security Groups:

In the EC2 dashboard, click “Security Groups” under “Network & Security”.

Click “Create security group”.

Configure Settings:

Name: “Nginx-Web-SG”.

Description: “Allows SSH and HTTP for Nginx web server”.

VPC: Select default VPC (e.g., “vpc-12345678”), matching the instance’s VPC.

Add Inbound Rules:

Click “Add rule”:

Type: “SSH” (TCP, port 22).

Source: “My IP” (e.g., 192.168.1.1/32). Use a CIDR (e.g., 203.0.113.0/24) for dynamic IPs cautiously.

Description: “SSH from my IP”.

Click “Add rule”:

Type: “HTTP” (TCP, port 80).

Source: “Anywhere-IPv4” (0.0.0.0/0).

Description: “Public HTTP access”.

Review Inbound Rules:

SSH: TCP, port 22, source: your IP.

HTTP: TCP, port 80, source: 0.0.0.0/0.

Step 4: Configure Outbound Rules
The default outbound rule allows all traffic, suitable for Nginx.

Check Default Rule:

In “Outbound rules”, verify:

Type: All traffic.

Protocol: All.

Port Range: All.

Destination: 0.0.0.0/0.

Customize (Optional):

For strict setups, add specific rules (e.g., HTTP to an API) and remove the default. Keep default for simplicity.
Stateful Benefit: Inbound HTTP allows outbound responses (e.g., webpage data) automatically.

Why Default?: Nginx needs outbound access for updates (apt update) or external connections.

Step 5: Save and Attach the Security Group
Save:

Review and click “Create security group”. “Nginx-Web-SG” appears in the list.
Attach:

Go to “Instances”, select “UbuntuNginxServer”.

Click “Actions” → “Networking” → “Change security groups”.

Check “Nginx-Web-SG”, uncheck the default Security Group.

Click “Save”.

Verify:

Confirm “Nginx-Web-SG” is listed under the instance’s Security Groups.
Step 6: Understanding Web Servers and Why Nginx Is Used
Before installing Nginx, let’s clarify what a web server is, why it’s needed, and why Nginx is chosen.

What Is a Web Server?: A web server is software that processes HTTP/HTTPS requests from clients (e.g., browsers) and delivers content (e.g., webpages, APIs). It operates at the OSI model’s Application layer, using TCP (Transport layer) on port 80 for HTTP and IP (Network layer) for addressing. Nginx, like Apache, listens for HTTP requests and responds with content, making it ideal for testing network configurations.

Why Do We Need a Web Server at This Stage?: The goal is to verify the Security Group’s HTTP rule (port 80, 0.0.0.0/0) allows public access to the EC2 instance. A web server:

Tests HTTP Access: Hosting a webpage confirms the Security Group permits inbound HTTP traffic, aligning with your OSI/TCP/IP focus on Application-layer protocols (HTTP).

Validates Security Group Rules: Browser access to the webpage proves the 0.0.0.0/0 source works, complementing SSH testing (restricted IP).

Mimics DevOps Scenarios: Web servers are common in cloud environments (e.g., hosting apps, dashboards), making this a practical exercise.

Offers Clear Feedback: A webpage load (e.g., Nginx’s default page) visually confirms the Security Group setup, unlike abstract tests (e.g., netcat).

Why Use Nginx Instead of Apache?:

Your Preference: You suggested Nginx, possibly due to its performance or relevance in modern DevOps (e.g., used by high-traffic sites like GitHub).

Performance and Modernity: Nginx is lightweight, handles high concurrency efficiently, and is optimized for static content, making it a forward-looking choice.

Simplicity for Testing: Nginx’s default Ubuntu setup serves a test page on port 80 with minimal configuration, perfectly suited to verify the HTTP rule.

Learning Value: Using Nginx exposes you to a popular alternative to Apache, enhancing your skills for diverse cloud setups.

No Functional Difference: Both Nginx and Apache listen on port 80, serving HTTP traffic to test the Security Group’s rule. The choice is stylistic for this task, as the Security Group is agnostic to the web server software.

Conclusion: Nginx is used to serve a test webpage, confirming the Security Group’s HTTP rule works, while offering performance benefits and a new learning experience. The setup remains simple, ensuring you focus on Security Groups rather than complex web server configuration.

Step 7: Install and Test Nginx
Install Nginx to test the HTTP rule.

Install Nginx:

SSH into the instance:


Copy

Copy
  ssh -i ~/aws-keys/nginx-key.pem ubuntu@<public-ip>
Replace <public-ip> with your instance’s IP (e.g., 54.123.45.67).

Run:


Copy

Copy
  sudo apt update
  sudo apt install nginx -y
  sudo systemctl start nginx
  sudo systemctl enable nginx
Customize Test Page (Optional):

Nginx’s default page is sufficient, but for clarity, create a custom page:


Copy

Copy
  echo "<h1>Hello from Nginx on Ubuntu EC2!</h1>" | sudo tee /var/www/html/index.html
Test HTTP Access:

Open a browser and visit http://<public-ip> (e.g., http://54.123.45.67).

You should see Nginx’s default page or “Hello from Nginx on Ubuntu EC2!”.

Troubleshooting:

If the page doesn’t load:

Verify HTTP rule allows 0.0.0.0/0 on port 80.

Check Nginx status: sudo systemctl status nginx.

Ensure instance is “Running”.

Step 8: Test SSH Connectivity
Verify the SSH rule restricts access.

Test SSH:

Reconnect if needed:


Copy

Copy
  ssh -i ~/aws-keys/nginx-key.pem ubuntu@<public-ip>
You should see the Ubuntu prompt.

Security Check:

Try SSH from another network (e.g., mobile data). It should fail due to “My IP”.

Troubleshooting:

Timeout: Check IP match in SSH rule.

Permission error: Verify chmod 400 nginx-key.pem.

Why Security Groups Are Essential
Security Groups secure EC2 instances by:

Precise Control: Filter by protocol, port, source (e.g., TCP port 80 from 0.0.0.0/0).

Stateful Simplicity: Auto-allow responses (e.g., Nginx’s HTTP replies).

Scalability: Apply to multiple instances.

Threat Protection: Block unauthorized access (e.g., deny port 3306).

Compliance: Support standards like PCI DSS.

Best Practices for Security Groups
Restrict SSH: Use “My IP” for port 22; avoid 0.0.0.0/0.

Limit Public Ports: Restrict sensitive ports (e.g., 5432) to specific sources.

Clear Naming: Use “Nginx-Web-SG” and tags (e.g., Key: “Role”, Value: “Web”).

Audit Regularly: Review rules via EC2 dashboard or AWS Config.

Segment Roles: Separate groups for web, database, etc.

Monitor: Log changes with CloudTrail.

Example Security Group Rules
For the Nginx web server:

Rule Type	Protocol	Port	Source/Destination	Description
Inbound	TCP	22	192.168.1.1/32	SSH from my IP
Inbound	TCP	80	0.0.0.0/0	Public HTTP access
Outbound	All	All	0.0.0.0/0	Allow all outbound
Conclusion
Launching an Ubuntu EC2 instance, configuring Security Groups for SSH and HTTP, and using Nginx to test HTTP access creates a secure web server. Nginx validates the Security Group’s HTTP rule while offering performance and learning benefits. Security Groups’ stateful filtering, tied to OSI/TCP/IP’s Network/Transport layers, ensures robust cloud security. Apply best practices to scale securely.

Hands-On Networking Commands for Cloud Troubleshooting
Networking commands like ping, traceroute, netstat, curl, dig, and nslookup are essential for diagnosing connectivity and services in cloud environments like AWS EC2. These tools help verify your Ubuntu EC2 instance’s Security Groups (e.g., SSH on port 22, HTTP on port 80) and troubleshoot issues, aligning with your OSI/TCP/IP studies. This Medium-friendly cheat sheet, tailored for DevOps beginners, includes examples using your EC2 instance (IP 54.123.45.67, running Nginx) and explains ICMP, the protocol powering ping and traceroute. It’s lightweight, respecting your limited MacBook storage, and packed with practical tips.

Understanding ICMP (Internet Control Message Protocol)
What is ICMP?
ICMP is a Network-layer protocol in the OSI and TCP/IP models, used for diagnostic and error-reporting tasks in IP networks. It’s part of the Internet Protocol suite, operating alongside TCP and UDP but without data payloads. ICMP messages, like echo requests or time-exceeded errors, help tools like ping and traceroute check connectivity and trace packet paths.

Role in Networking Commands:

ping: Sends ICMP Echo Request (type 8) packets and expects Echo Reply (type 0) to confirm a host is reachable.

traceroute/tracert: Uses ICMP Time Exceeded (type 11) messages (or UDP probes) to map hops by incrementing TTL (Time to Live).

Why Important for EC2?:

ICMP is critical for testing basic connectivity to your EC2 instance (e.g., 54.123.45.67) before SSH or HTTP access.

AWS Security Groups block ICMP by default, so you may need to add an ICMP rule (e.g., allow “All ICMP - IPv4” from your IP) to enable ping or traceroute.

OSI/TCP/IP Layer: Network layer (runs over IP, protocol number 1).

Example Use: If ping 54.123.45.67 fails, an ICMP rule may be missing, or the instance may be offline, guiding further troubleshooting.

Security Note: Limit ICMP access in Security Groups (e.g., to your IP) to prevent abuse, like DDoS attacks using ICMP floods.

Why It Matters: Understanding ICMP helps you interpret ping and traceroute outputs, diagnose EC2 network issues, and configure Security Groups effectively.

Networking Commands Cheat Sheet
🟢 ping
Purpose: ping sends ICMP Echo Request packets to test if a host, like your EC2 instance, is reachable. It’s a quick way to verify server uptime or spot network issues at the Network layer, often the first step before SSH or HTTP tests.

Why Use?: Checks if your EC2’s public IP responds, helping debug Security Group ICMP rules or instance status.

Example: Ping your EC2 instance.


Copy

Copy
  ping 54.123.45.67 -c 4
Output (if successful):


Copy

Copy
  PING 54.123.45.67 (54.123.45.67) 56(84) bytes of data.
  64 bytes from 54.123.45.67: icmp_seq=1 ttl=50 time=25.1 ms
  ...
  4 packets transmitted, 4 received, 0% packet loss
OSI/TCP/IP: Network layer (ICMP Echo Request/Reply).

ICMP Role: Uses ICMP type 8 (request) and type 0 (reply) to confirm reachability.

Tip: If ping fails, add an ICMP rule to your Security Group (e.g., “All ICMP - IPv4” from 192.168.1.1/32).

🧭 traceroute (Linux/macOS) / tracert (Windows)
Purpose: traceroute (or tracert) traces the packet path to a destination, showing each router hop and latency. It uses ICMP Time Exceeded messages to identify routing issues, like ISP blocks or AWS VPC misconfigurations, at the Network layer.

Why Use?: Pinpoints where connectivity to your EC2 fails (e.g., before SSH or HTTP).

Example: Trace the path to your EC2.


Copy

Copy
  traceroute 54.123.45.67
Output (simplified):


Copy

Copy
  traceroute to 54.123.45.67, 30 hops max
   1  192.168.1.1  1.2 ms
   2  10.0.0.1  5.6 ms
   ...
  10  ec2-54-123-45-67.compute-1.amazonaws.com  25.0 ms
OSI/TCP/IP: Network layer (ICMP or UDP).

ICMP Role: Relies on ICMP Time Exceeded (type 11) for TTL-expired packets at each hop.

Tip: Some hops show * * * (ICMP blocked); add an ICMP rule if traceroute fails to reach your EC2.

📊 netstat
Purpose: netstat displays active connections, listening ports, and services on your EC2 instance. It’s ideal for verifying Nginx (port 80) or SSH (port 22) services are running, aiding Security Group troubleshooting at the Transport/Application layers.

Why Use?: Confirms your EC2’s ports match Security Group rules.

Example: Check listening ports on your EC2.


Copy

Copy
  ssh -i ~/aws-keys/nginx-key.pem ubuntu@54.123.45.67
  sudo apt install net-tools -y
  netstat -tuln
Output:


Copy

Copy
  Proto Recv-Q Send-Q Local Address  Foreign Address  State
  tcp        0      0 0.0.0.0:22     0.0.0.0:*        LISTEN
  tcp        0      0 0.0.0.0:80     0.0.0.0:*        LISTEN
OSI/TCP/IP: Transport (TCP/UDP ports) and Application (services).

ICMP Role: None; netstat focuses on TCP/UDP, not ICMP.

Tip: If port 80 isn’t listed, restart Nginx (sudo systemctl restart nginx).

🌐 curl
Purpose: curl sends HTTP/HTTPS requests to web servers, retrieving responses like your EC2’s Nginx webpage. It’s perfect for testing APIs or validating Security Group HTTP rules at the Application layer.

Why Use?: Verifies your EC2’s HTTP access (port 80) works publicly.

Example: Fetch your EC2’s webpage.


Copy

Copy
  curl http://54.123.45.67
Output:


Copy

Copy
  <h1>Hello from Nginx on Ubuntu EC2!</h1>
Header Check:


Copy

Copy
  curl -I http://54.123.45.67
Output:


Copy

Copy
  HTTP/1.1 200 OK
  Server: nginx/1.18.0 (Ubuntu)
  Content-Type: text/html
  ...
OSI/TCP/IP: Application layer (HTTP over TCP).

ICMP Role: None; curl uses TCP, but ping (ICMP) can confirm connectivity first.

Tip: If curl fails, check Security Group HTTP rule (0.0.0.0/0, port 80) or Nginx status.

🔍 dig
Purpose: dig performs detailed DNS lookups, retrieving records like A (IP address) for domains linked to your EC2. It’s essential for troubleshooting DNS resolution, especially with AWS Route 53, at the Application layer.

Why Use?: Ensures a domain (e.g., myapp.example.com) resolves to your EC2’s IP.

Example: Query a domain.


Copy

Copy
  dig myapp.example.com
Output (simplified):


Copy

Copy
  ;; ANSWER SECTION:
  myapp.example.com. 300 IN A 54.123.45.67
OSI/TCP/IP: Application layer (DNS over UDP/TCP).

ICMP Role: None; DNS uses UDP/TCP, but ICMP (ping) can verify the resolved IP.

Tip: Use dig @8.8.8.8 myapp.example.com to test Google’s DNS.

🔎 nslookup
Purpose: nslookup is a simple DNS query tool for resolving domains to IPs, great for quick checks on Windows or Linux. It helps verify EC2 domain mappings at the Application layer.

Why Use?: Confirms your EC2’s domain resolves correctly.

Example: Resolve a domain.


Copy

Copy
  nslookup myapp.example.com
Output:


Copy

Copy
  Server:         8.8.8.8
  Address:        8.8.8.8#53
  Name:   myapp.example.com
  Address: 54.123.45.67
OSI/TCP/IP: Application layer (DNS).

ICMP Role: None; use ping to test the resolved IP.

Tip: Try nslookup myapp.example.com 1.1.1.1 if resolution fails.

Tips for Effective Use
Run Locations:

Locally: ping, traceroute, curl, dig, nslookup to test EC2 connectivity.

On EC2 (via SSH): netstat to check server ports.

Install on Ubuntu EC2:

Pre-installed: ping, curl, traceroute.

Install: sudo apt install net-tools (netstat), sudo apt install dnsutils (dig).

Security Group for ICMP:

Add an ICMP rule (e.g., “All ICMP - IPv4” from your IP) for ping and traceroute.

Your current SSH (port 22) and HTTP (port 80) rules support curl, netstat.

Storage: Commands generate no persistent files unless you save outputs (e.g., curl http://54.123.45.67 > page.html). Keep minimal logs.

OSI/TCP/IP Troubleshooting:

Network: ping, traceroute (ICMP).

Transport/Application: netstat (ports), curl (HTTP), dig/nslookup (DNS).

Conclusion
With ping, traceroute, netstat, curl, dig, and nslookup, you can troubleshoot your AWS EC2 instance like a pro. ICMP powers ping and traceroute, helping you verify connectivity and routing to your Nginx server. These commands, rooted in OSI/TCP/IP layers, streamline DevOps tasks and ensure your Security Groups work. Keep this cheat sheet handy for cloud networking success.
