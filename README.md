# EX01 Developing a Simple Webserver
## Date: 06/10/2023

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
	<title> Revenue chart </title>
	<body>
		<table border="2" cellspacing="2" cellpadding="3">
			<caption> Top five highest revenue generating software companies </caption>
				<tr>
					<td> Serial Number </td>
					<td> Companies </td>
					<td> Revenue Generated </td>
				</tr>
				<tr>
					<td> 1, </td>
					<td> Microsoft </td>
					<td> $203.08 billion </td>
				</tr>
				<tr>
					<td> 2, </td>
					<td> Oracle </td>
					<td> $46.07 billion </td>
				</tr>
				<tr>
					<td> 3, </td>
					<td> SAP </td>
					<td> $32.97 billion </td>
				</tr>		
				<tr>
					<td> 4, </td>
					<td> Salesforce </td>
					<td> $30.29 billion </td>
				</tr>
				<tr>
					<td> 5, </td>
					<td> Adobe </td>
					<td> $17.61 billion </td>
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

```
## OUTPUT:
![Screenshot 2023-11-07 170035](https://github.com/Gokkul-M/simplewebserver/assets/144870543/8d5cf588-d682-45e6-8a29-93aedf822118)
![Screenshot 2023-11-07 170124](https://github.com/Gokkul-M/simplewebserver/assets/144870543/89518073-343a-47d0-b957-5a6a13e5d910)


## RESULT:
The program for implementing simple webserver is executed successfully.
