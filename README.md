# EX01 Developing a Simple Webserver
## Date:

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
from http.server import HTTPServer, BaseHTTPRequestHandler

html_content = """
<!doctype html>
<html>
<head>
    <title>My Web Server</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        h1 {
            text-align: center;
        }
        table {
            border-collapse: collapse;
            width: 80%;
            margin: auto;
        }
        th, td {
            border: 2px solid black;
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: lightgreen;
        }
        tr:nth-child(even) {
            background-color: #ccffcc;
        }
    </style>
</head>
<body>
    <h1>TCP/IP Protocol</h1>
    <table>
        <tr>
            <th>S.no</th>
            <th>Layer</th>
            <th>Protocols</th>
        </tr>
        <tr>
            <td>1.</td>
            <td><b>Application Layer</b></td>
            <td>HTTP, HTTPS, FTP, SMTP, POP3, IMAP, DNS, Telnet, SSH</td>
        </tr>
        <tr>
            <td>2.</td>
            <td><b>Transport Layer</b></td>
            <td>TCP (Transmission Control Protocol), UDP (User Datagram Protocol)</td>
        </tr>
        <tr>
            <td>3.</td>
            <td><b>Network Layer (Internet Layer in TCP/IP)</b></td>
            <td>IP (IPv4, IPv6), ICMP, IGMP, ARP, RARP</td>
        </tr>
        <tr>
            <td>4.</td>
            <td><b>Link Layer (Network Access Layer in TCP/IP)</b></td>
            <td>Ethernet</td>
        </tr>
    </table>
</body>
</html>
"""

class SimpleHTTPRequestHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        self.send_response(200)
        self.send_header("Content-type", "text/html")
        self.end_headers()
        self.wfile.write(html_content.encode("utf-8"))

if __name__ == "__main__":
    server_address = ("", 5000)  
    httpd = HTTPServer(server_address, SimpleHTTPRequestHandler)
    print("Server running on http://localhost:5000")
    httpd.serve_forever()



## OUTPUT:
<img width="1920" height="1080" alt="Screenshot 2025-08-29 094054" src="https://github.com/user-attachments/assets/4ad15a70-bcff-4c98-bd47-cc06e6f41632" />



## RESULT:
The program for implementing simple webserver is executed successfully.
