# Web Notes

* REST (Representation State Transfer) is a term we have thrown around a lot in the course.
  ### [Reading here](https://codewords.recurse.com/issues/five/what-restful-actually-means)

  * It is a set of design principles for making network communication more scalable and flexible.
  * These principles answer a number of questions.
  * What are the components of the system?
  * How should they communicate with each other?
  * How do we ensure we can swap out different parts of the system at any time?
  * How can the system be scaled up to serve billions of users?

## Stateless

Stateless does not mean that servers and clients do not have state, it simply means that they do not need to keep track of each other’s state. When a client is not interacting with the server, the server has no idea of its existence. The server also does not keep a record of past requests. Each request is treated as a standalone.

### What Happens When You Type in Google.com and press Enter

1. You type maps.google.com into the address bar of your browser.

2. The browser checks the cache for a DNS record to find the corresponding IP address of maps.google.com.

DNS(Domain Name System) is a database that maintains the name of the website (URL) and the particular IP address it links to. Every single URL on the internet has a unique IP address assigned to it. The IP address belongs to the computer which hosts the server of the website we are requesting to access. For an example, www.google.com has an IP address of 209.85.227.104. So if you’d like you can reach www.google.com by typing http://209.85.227.104 on your browser. DNS is a list of URLs and their IP addresses just like how a phone book is a list of names and their corresponding phone numbers.

DNS makes it easier to understand URLs, rather than having URLs strictly be their numeric IP addresses.

3. If the requested URL is not in the cache, ISP’s DNS server initiates a DNS query to find the IP address of the server that hosts maps.google.com.

4. Browser initiates a TCP connection with the server.

5. The browser sends an HTTP request to the web server.

6. The server handles the request and sends back a response.

7. The server sends out an HTTP response.

8. The browser displays the HTML content (for HTML responses which is the most common).
