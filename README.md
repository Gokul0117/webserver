# Developing a Simple Webserver

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```python
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
<h2>4. Angular </h2>
<h2>5. Spring </h2>
</body>
</html> 
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

## OUTPUT:
### Server output
![Screenshot 2023-03-30 090404](https://user-images.githubusercontent.com/121165938/228723061-72e6c867-d448-422e-bc07-7d33ba2b0e9b.png)
### Client output
![Screenshot 2023-03-30 085918](https://user-images.githubusercontent.com/121165938/228723404-fa7886e0-9120-48f0-8c67-a8d3ce0bf6f7.png)



## RESULT:
The program is executed succesfully
