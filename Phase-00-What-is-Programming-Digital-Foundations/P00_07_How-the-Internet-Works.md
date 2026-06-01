## What Is This?
The internet is a global network of interconnected computers that communicate with each other to share information. Imagine a huge library where each bookshelf represents a computer, and the books on the shelves are the information stored on those computers. When you want to access information from another bookshelf, you send a message to the librarian, who then retrieves the book and sends it back to you. This process is similar to how the internet works, where computers send and receive information to and from each other.

## How It Works Internally
### LAYER 1: Minimum Viable Version
The internet works by assigning a unique identity to every device on a network, known as an IP address. This IP address is like a street address that allows devices to find and communicate with each other. 
### IP Addresses
IP addresses are used to identify devices on a network, and they are unique to each device. 
### IPv4 vs IPv6
There are two types of IP addresses: IPv4 and IPv6. IPv4 is the older version and uses 32-bit addresses, while IPv6 is the newer version and uses 128-bit addresses. 
### DNS — Domain Name System
When you type a website's domain name into your browser, the Domain Name System (DNS) translates that name into the website's IP address. This is like looking up a person's name in a phone book to find their phone number. 
### TCP vs UDP
Once the IP address is resolved, the data is sent over the internet using either the Transmission Control Protocol (TCP) or the User Datagram Protocol (UDP). TCP is a reliable protocol that ensures data is delivered in the correct order, while UDP is a faster protocol that prioritizes speed over reliability. 
### The TCP 3-way Handshake
When using TCP, a three-way handshake is used to establish a connection between devices. This involves the client sending a SYN (synchronize) packet, the server responding with a SYN-ACK (synchronize-acknowledgment) packet, and the client responding with an ACK (acknowledgment) packet. 
### HTTP vs HTTPS
The Hypertext Transfer Protocol (HTTP) is used to transfer data over the internet, but it is not secure. The Hypertext Transfer Protocol Secure (HTTPS) is a secure version of HTTP that uses encryption to protect data. 
### TLS/SSL
HTTPS uses Transport Layer Security (TLS) or Secure Sockets Layer (SSL) to encrypt data. This is like sending a secret message in a locked box that only the intended recipient can open. 
### HTTP Request Structure
An HTTP request consists of a method (such as GET or POST), a URL, headers, and a body. The method specifies the action to be taken, the URL specifies the resource to be accessed, the headers provide additional information, and the body contains the data to be sent. 
### HTTP Response Structure
An HTTP response consists of a status code, headers, and a body. The status code indicates the result of the request, the headers provide additional information, and the body contains the data returned by the server. 
### Common Status Codes
Common status codes include 200 (OK), 201 (Created), 301 (Moved Permanently), 400 (Bad Request), 401 (Unauthorized), 403 (Forbidden), 404 (Not Found), and 500 (Internal Server Error). 
### REST — Representational State Transfer
The Representational State Transfer (REST) architecture is used to design networked applications. It is based on the idea of resources, which are identified by URIs, and can be manipulated using a fixed set of operations. 
### Client-Server Model
The client-server model is a distributed application structure where one program, the client, requests a service or resource from another program, the server. 
### WebSockets
WebSockets provide a persistent, bidirectional communication channel between a client and a server over the web. This allows for real-time communication and is useful for applications such as live updates and gaming. 
### CDN — Content Delivery Networks
A Content Delivery Network (CDN) is a network of distributed servers that deliver web content to users based on their geographic location. This can improve the speed and reliability of web applications. 
### Latency vs Bandwidth vs Throughput
Latency refers to the delay between the time data is sent and the time it is received. Bandwidth refers to the amount of data that can be sent per unit of time. Throughput refers to the actual amount of data that is sent per unit of time, taking into account factors such as latency and packet loss.

## Syntax and Structure
```text
# STEP 1: Assign a unique IP address to each device on the network
# STEP 2: Use DNS to translate domain names into IP addresses
# STEP 3: Choose a transport protocol (TCP or UDP) to send data
# STEP 4: Establish a connection using the TCP 3-way handshake (if using TCP)
# STEP 5: Send an HTTP request with the correct method, URL, headers, and body
# STEP 6: Receive an HTTP response with a status code, headers, and body
In Phase 1 we will write this in real code.
```

## How This Connects to the Project
Before learning about how the internet works, the project looked like a simple network diagram with no understanding of how devices communicate with each other. After learning about how the internet works, the project now includes a detailed network diagram that shows how devices use IP addresses, DNS, TCP/UDP, and HTTP to communicate with each other. The exact file and function name where this concept lives in the project is the `NetworkDiagram.java` file, which contains the `createNetworkDiagram()` function. A real company that uses this exact pattern is Google, which uses a complex network of servers and data centers to provide its services to users around the world.

## Common Mistakes Beginners Make
**Wrong idea:** Thinking that IP addresses are not unique to each device.
**Correct idea:** IP addresses are unique to each device and are used to identify devices on a network.
Wrong idea: Using HTTP instead of HTTPS for secure data transfer.
Correct idea: HTTPS is a secure version of HTTP that uses encryption to protect data.
Looks right but is silently wrong: Using the wrong transport protocol (TCP or UDP) for a specific application.
Seems optional but critical at scale: Not using a CDN to distribute web content to users based on their geographic location.
Missed config or flag: Not configuring the DNS settings correctly.
Interview question: How does the internet work, and what are the differences between TCP and UDP?

## Verification Task 1
Your system shows a "connection refused" error when trying to access a website. You have the website's IP address and DNS settings. Diagnose and fix the issue.
## Solution 1
The issue is likely due to a misconfigured DNS setting or a firewall blocking the connection. To fix the issue, check the DNS settings and ensure that the IP address is correct. Also, check the firewall settings to ensure that the connection is not being blocked.

## Verification Task 2
You are building a real-time gaming application and need to choose a transport protocol. Use TCP or UDP and defend your choice using this topic.
## Solution 2
I would choose UDP as the transport protocol for the real-time gaming application. This is because UDP prioritizes speed over reliability, which is critical for real-time applications where latency can be a major issue. While TCP provides reliable data transfer, it can introduce latency due to its acknowledgment mechanism, which can be detrimental to real-time applications.

## Verification Task 3
You are reviewing a code snippet that uses HTTP to transfer sensitive data. Find and fix the bug.
## Solution 3
The bug is that the code snippet is using HTTP instead of HTTPS to transfer sensitive data. To fix the bug, replace the HTTP protocol with HTTPS, which provides encryption to protect the data.

## What Comes Next
The next topic is "What is Programming?" which follows logically from this one because understanding how the internet works provides a foundation for learning about programming concepts such as data transfer, networking, and security. This matters to you because without a solid understanding of how the internet works, you will struggle to build secure and efficient networked applications.

## Reference Summary
The internet is a global network of interconnected computers that communicate with each other to share information. IP addresses are used to identify devices on a network, and DNS translates domain names into IP addresses. TCP and UDP are transport protocols used to send data over the internet, with TCP providing reliable data transfer and UDP prioritizing speed. HTTP and HTTPS are used to transfer data over the internet, with HTTPS providing encryption to protect data. Common status codes include 200, 201, 301, 400, 401, 403, 404, and 500. The client-server model is a distributed application structure where one program requests a service or resource from another program. WebSockets provide a persistent, bidirectional communication channel between a client and a server. CDNs distribute web content to users based on their geographic location, improving speed and reliability. Understanding how the internet works is critical for building secure and efficient networked applications, and is a foundation for learning about programming concepts such as data transfer, networking, and security.