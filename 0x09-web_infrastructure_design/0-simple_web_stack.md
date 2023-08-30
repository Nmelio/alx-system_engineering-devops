****DESCRIPTION:****

One server web infrastructure that hosts the website that is reachable via www.foobar.com with and IP address 8.8.8.8.

****EXPLANATION OF SOME SPECIFICS ABOUT THIS INFRASTRUCTURE:****

**What is a server?**
A server is a computer hardware or software that provides services to other computers, which are usually referred to as clients.

**What is the role of the domain name?**
They are easy-to-remember aliases of IP addresses.

**What type of DNS record www is in www.foobar.com?**
It is in an A-record. A-record uses IPv4 addresses, and 8.8.8.8 is and IPv4 address.

**What is the role of the web server?**
The web server accepts HTTP/HTTPS requests, which it sends to the appropriate servers, retrieves the response and sends its HTTP/HTTPS formats back to the originator of the request, if not possible then it send an error message.

**What is the role of the application server?**
To retrieve and execute requests sent through the web server. It communicates with and required databases and applications requires.

**What is the role of the database?**
To maintain a collection of organized information that can easily be accessed, managed and updated.

**What is the server using to communicate with the computer of the user requesting the website?**
It communicates through the TCP/IP protocol suite over the internet.

****ISSUES WITH THIS INFRASTRUCTURE:****

**SPOF:**
There are multiple points of failure. The web server, application server and MySQL database servers have no alternate servers in case of failure.
**Downtime when maintenance needed (like deploying new code web server needs to be restarted):**
Due to the fact that there are no alternate servers, deploying new codes will lead to downtimes.
**Cannot scale if too much incoming traffic:**
Since only one server is used, it can easily run out of resources.
