# EX01 Developing a Simple Webserver
## Date:18/10/2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
    <title>
        Device Specification
    </title>
    <body>
        <h1 align="center"> Device Specification<i>(gokul 24002047)</i></h1>
        <ol>
            <li><b>Device name</b> : gokul</li>

            <li><b>Processor</b> : 12th Gen Intel(R) Core(TM) i5-12450H 2.00 GHz</li>

            <li><b>Installed RAM</b> : 16.0 GB (15.7 GB usable)</li>

            <li><b>Device ID</b> : FFF0125F-0D62-498B-829E-F7CF63C26C41</li>

            <li><b>Product ID</b> : 00342-42699-71135-AAOEM</li>

            <li><b>System type</b> : 64-bit operating system, x64-based processor</li>

            <li><b>Pen and touch</b> : No pen or touch input is available for this display</li>
        </ol>
    </body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![Screenshot 2024-11-14 194023](https://github.com/user-attachments/assets/281dc65c-9cf3-4d9c-8f52-669c9c417bb6)

![Screenshot (3)](https://github.com/user-attachments/assets/dbc704e8-c128-4d91-afd9-e669dd61c35e)


## RESULT:
The program for implementing simple webserver is executed successfully.
