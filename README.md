# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

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
~~~
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<title> Simplewebserver </title>
<body>
<table border="3" cellspacing="12">
<caption> Top Five Revenue Generating Software Companies </caption>

<tr>
<th>S.No</th>
<th>Company</th>
<th>Revenue</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft</td>
<td>65 Billion</td>
</tr>
<tr>
<td>2</td>
<td>Oracle</td>
<td>29.6 Billion</td>
</tr>
<tr>
<td>3</td>
<td>IBM</td>
<td>29.1 Billion</td>
</tr>
<tr>
<td>4</td>
<td>SAP</td>
<td>6.4 Billion</td>
</tr>
<tr>
<td>5</td>
<td>Symantec</td>
<td>5.6 Billion</td>
</tr>
</table>
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
~~~




## OUTPUT:

![Screenshot 2024-01-02 032014](https://github.com/nareshofficial/simplewebserver/assets/155141830/ea999e85-8f5e-4ed7-8f36-c35059645c35)

## RESULT:
The program for implementing simple webserver is executed successfully.
