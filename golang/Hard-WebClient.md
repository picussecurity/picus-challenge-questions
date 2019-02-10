### Description
Write a web client from scratch. Requirements:

* Given an HTTP URL (no need to support TLS or HTTPS), fetch the content using a GET request
* Display the content on the console (a'la curl)
* Exit

For the challenge, your requirements are similar to the HTTP server challenge - implement a thing you use often from scratch instead of using your language's built in functionality:

* You may not use any of your language's built in web client functionality or any third party library or tool. E.g. you can't use Go's "net/http", "net/url", or a third-party module like requests or curl. Same for any other language and their built in features; you may also not shell out to something like curl (e.g. no system("curl %s", url)).
* Your program should use string processing calls to dissect the URL (again, you cannot use any of the built in functionality like Go's "net/url" module or third-party URL parsing libraries like urlparse).
* Your program should support non-standard ports (for instance http://server.io:8080/).
* Your program does NOT need to support TLS or SSL.
* Your program should use low level socket() calls (or equivalent) to connect to the server, and make a well-formatted HTTP/1.1 request. That's the whole point of the challenge!

A good test server is httpbin, which can give you all sorts of feedback about your client's behavior; another is requestb.in.


### Example Output
Here is some simple bare-bones output from httpbin.org:
```
HTTP/1.1 200 OK
Connection: keep-alive
Server: meinheld/0.6.1
Date: Fri, 15 Dec 2017 17:14:03 GMT
Content-Type: application/json
Access-Control-Allow-Origin: *
Access-Control-Allow-Credentials: true
X-Powered-By: Flask
X-Processed-Time: 0.00114393234253
Content-Length: 158
Via: 1.1 vegur

{
  "args": {},
  "headers": {
    "Connection": "close",
    "Host": "httpbin.org"
  },
  "origin": "1.2.3.4",
  "url": "http://httpbin.org/get"
}
``