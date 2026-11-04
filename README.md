# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM

#echo_sever.py

import socket
server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

server.bind(('localhost', 5000))


server.listen(1)

print("Server is waiting for connection...")

conn, addr = server.accept()

print("Connected by:", addr)

while True:
    # Receive data from client
    data = conn.recv(1024).decode()

    if not data:
        break

    print("Client:", data)

    conn.send(data.encode())

conn.close()
server.close()
## OUPUT
## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
