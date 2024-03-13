# EX01 Developing a Simple Webserver
## Date:16-02-2024

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
<head>
<title>Top Software companies with revenue table</title>
</head>
<body bgcolor="aquamarine">
<table bgcolor="aqua" border="5" cellspacing="6" cellpadding="10" align="center" >
<caption>TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES</caption>
	<tr bgcolor="lawngreen">
		<th>Rank</th>
		<th>Company</th>
		<th>Sales</th>
		<th>Naionality</th>
	</tr>
	
	<tr bgcolor="pink">
		<td>1</td>
		<td>Microsoft</td>
		<td>57.9</td>
		<td>USA</td>
	</tr>

	<tr bgcolor="pink">
		<td>2</td>
		<td>Oracle</td>
		<td>21.0</td>
		<td>USA</td>
	</tr>

	<tr bgcolor="pink">
		<td>3</td>
		<td>SAP</td>
		<td>16.1</td>
		<td>Germany</td>
	</tr>
	
	<tr bgcolor="pink">
		<td>4</td>
		<td>Computer Associates</td>
		<td>4.1</td>
		<td>USA</td>
	</tr>

	<tr bgcolor="pink">
		<td>5</td>
		<td>Adobe</td>
		<td>3.4</td>
		<td>USA</td>
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
![image](https://github.com/ibrahimfedahs/simplewebserver/assets/150319493/e2fa4c95-0c4c-414a-ba08-6da6cb2cdc06)
![image-1](https://github.com/ibrahimfedahs/simplewebserver/assets/150319493/5295123a-5fda-4583-9860-794e2354eb7e)


## RESULT:
The program for implementing simple webserver is executed successfully.
