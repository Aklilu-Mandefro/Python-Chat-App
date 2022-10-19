<hr>

<h1 align="left">Hey there, I'm <a href="https://volunteer-tech.com/Aklilu">Aklilu </a><img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="28"> 
 <a href="https://github.com/harismuneer/Ultimate-Facebook-Scraper"><img align="right" src="https://volunteer-tech.com/Aklilu/uploads/gallery/202205/image_500x_6273d3aaa57de.jpg" alt="Developer's Profile" width="200"/></a> - A Tech Enthusiast </h1> 


#### I love coding and most of my time goes into learning the best ways to write clean code. When I am not at my desk, I can be seen helping out tech geeks and writing software engineering contents. I am always open to help others.

#### I am passionate about creating an impact. Helping others and seeing their happiness and success because of me is what makes me eternally grateful.
<hr>

<h2 align="left">🌐 Stay Connected</h2>
<p align="left">
  <a href="https://www.linkedin.com/in/aklilu-mandefro-messele-8a3681194/"><img title="Follow on LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"/></a>
  <a href="https://twitter.com/AkliluMandefro"><img title="Follow on Twitter" src="https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white"/></a>
  <a href="mailto:aklilu.mandefro@volunteer-tech.com"><img title="Email" src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"/></a>
  <a href="https://github.com/Aklilu-Mandefro"><img title="Follow on GitHub" src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white"/></a>
  <a href="https://www.instagram.com/aklilumandefro/"><img title="Follow on Instagram" src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"/></a>
</p>


### Let's get started!


# Python Chat Application

It is a simple project and contains two python scripts server.py which handle client request and client.py send request and receive response from the server through socket communication.

## Prerequisites

In order to run the python script, your system must have the following programs/packages installed and the contact number should be saved in your phone (You can use bulk contact number saving procedure of email). There is a way without saving the contact number but has the limitation to send the attachment.
* Python 3.8

## Approach
* server.py needed to execute in terminal. 
* client.py needed to execute from the client machine and enter the hostname or IP address.
* the server will establish connection between the server and the client through socket.
* now from the server or client text can be sent.

## Server Code
```
# Program to accept client request
# Author @inforkgodara

import socket

s = socket.socket()
host = socket.gethostname()
print(' Server will start on host : ', host)
port = 8080
s.bind((host, port))
print()
print('Waiting for connection')
print()
s.listen(1)
conn, addr = s.accept()
print(addr, ' Has connected to the server')
print()
while 1:
    message = input(str('>> '))
    message = message.encode()
    conn.send(message)
    print('Sent')
    print()
    incoming_message = conn.recv(1024)
    incoming_message = incoming_message.decode()
    print(' Client : ', incoming_message)
    print()
```
## Client Code
```
# Program to send request to the server
# Author @inforkgodara

import socket

s = socket.socket()
host = input(str('Enter hostname or host IP : '))
port = 8080
s.connect((host, port))
print('Connected to chat server')
while 1:
    incoming_message = s.recv(1024)
    incoming_message = incoming_message.decode()
    print(' Server : ', incoming_message)
    print()
    message = input(str('>> '))
    message = message.encode()
    s.send(message)
    print('Sent')
    print()
```
