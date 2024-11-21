# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
from http.server import BaseHTTPRequestHandler, HTTPServer

class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        
        # Define the content (the HTML response)
        content = """
        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
            <title>College Timetable</title>
            <style>
                table {
                    width: 100%;
                    border-collapse: collapse;
                }
                th, td {
                    padding: 8px;
                    text-align: center;
                }
                th {
                    background-color: #f2f2f2;
                }
            </style>
        </head>
        <body>

        <h1>College Timetable</h1>

        <table border="1">
            <tr>
                <th>Time</th>
                <th>08 - 10</th>
                <th>10 - 12</th>
                <th>12 - 01</th>
                <th>01 - 03</th>
                <th>03 - 05</th>
            </tr>
            <tr>
                <th>Monday</th>
                <td></td>
                <td>Web</td>
                <td>L</td>
                <td>C</td>
                <td></td>
            </tr>
            <tr>
                <th>Tuesday</th>
                <td>Career</td>
                <td>D.E.</td>
                <td>U</td>
                <td>Chem</td>
                <td></td>
            </tr>
            <tr>
                <th>Wednesday</th>
                <td>C</td>
                <td></td>
                <td>N</td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <th>Thursday</th>
                <td>EDM</td>
                <td></td>
                <td>C</td>
                <td>Web</td>
                <td></td>
            </tr>
            <tr>
                <th>Friday</th>
                <td>Chem</td>
                <td>Math</td>
                <td>H</td>
                <td>D.E.</td>
                <td></td>
            </tr>
            <tr>
                <th>Saturday</th>
                <td>EDM</td>
                <td></td>
                <td>H</td>
                <td>Math</td>
                <td>Web</td>
            </tr>
        </table>

        </body>
        </html>
        """
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
# OUTPUT:
![Screenshot 2024-11-21 180339](https://github.com/user-attachments/assets/ab963bb6-df15-48f9-9ec3-b31ce51c695b)
![Screenshot 2024-11-21 180413](https://github.com/user-attachments/assets/990d10b7-eab2-4065-b945-95b9de89d71a)


# RESULT:

The program for implementing simple webserver is executed successfully.
