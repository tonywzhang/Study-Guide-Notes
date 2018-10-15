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

#### How does DNS Work?

The Domain Name System is one of the most important and over-looked parts of the internet.

Without it, the internet as we know it would collapse.

So many services we get from the internet that we take for granted would not be available to us as we know it.

When you type www.example.com, additional non-viewable characters are added to the end of that domain string entry, and the DNS looks up that domain name for a matching IP address in it's record books.

But before that even takes place, the browser and operating system will first check their respective cache's to make sure they don't already have local knowledge of what that domain name holds.

If they both do not know, the operating system asks a name server for IP addresses it does not know. The operating system queries the name server for the domain name. If it still can't find the root domain name within the name service, we move on to the next step.

The operating system will then be directed to the Top Level Domain name servers, TLD name servers for short.

If this also fails, we will be directed to the authoritative name servers. When a website is purchased, the registrar is told which authoritative name servers that domain should use.

When it finally is successfully found, the reply is given to the operating system to give to the browser with the correct IP address.

There are many steps included in this process, but it was designed to be extremely fast and efficient.

If anyone were to change any part or filter any part of the DNS process, the internet would crash and be doomed.

### HTTP Methods

#### GET

The GET method is used to retrieve information from the given server using a given URI. Requests using GET should only retrieve data and should have no other effect on the data.

#### POST

A POST request is used to send data to the server, for example, customer information, file upload, etc. using HTML forms.

#### DELETE

Removes all current representations of the target resource given by a URI.


### What is AJAX?

AJAX = Asynchronous JavaScript And XML.

AJAX is not a programming language.

AJAX just uses a combination of:

  * A browser built-in XMLHttpRequest object (to request data from a web server)
  * JavaScript and HTML DOM (to display or use the data)

AJAX allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page.
