# EX01 Developing a Simple Webserver
## Name:YASHWANTH R
## Reg no:212224240188
## Date:28.05.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
HTML
```
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<table border="1" align="center" cellpadding="10" bgcolor="blue">
<caption><h1>List of Protocols in TCP/IP Protocol Suite</h1></caption>
<tr>
   <th>S.No.</th><th>Name of the Layer</th><th>Name of the Protocol</th>
</tr>
<tr>
   <td>1.</td><td>Application Layer</td> <td>HTTP, FTP, DNS, Telnet</td>
</tr>
<tr>
   <td>2.</td><td>Transport Layer</td> <td>TCP & UDP</td>
</tr>
<tr>
    <td>3.</td><td>Network layer</td> <td>IPV4/IPV6</td>
</tr>
<tr>
    <td>4.</td><td>Link layer</td> <td>Ethernet</td>
</tr>
</table>
</body>
</html>
```
PYTHON
```
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<table border="1" align="center" cellpadding="10" bgcolor="blue">
<caption><h1>List of Protocols in TCP/IP Protocol Suite</h1></caption>
<tr>
   <th>S.No.</th><th>Name of the Layer</th><th>Name of the Protocol</th>
</tr>
<tr>
   <td>1.</td><td>Application Layer</td> <td>HTTP, FTP, DNS, Telnet</td>
</tr>
<tr>
   <td>2.</td><td>Transport Layer</td> <td>TCP & UDP</td>
</tr>
<tr>
    <td>3.</td><td>Network layer</td> <td>IPV4/IPV6</td>
</tr>
<tr>
    <td>4.</td><td>Link layer</td> <td>Ethernet</td>
</tr>
</table>
</body>
</html>
"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


## OUTPUT:
<img width="1666" height="1167" alt="image" src="https://github.com/user-attachments/assets/056b3fae-f333-44bf-8e26-c7d7d5930d82" />



## RESULT:
The program for implementing simple webserver is executed successfully.
