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

#echo_client.py

import socket
client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

client.connect(('localhost', 5000))

while True:
    
    msg = input("Enter message: ")

    client.send(msg.encode())

    data = client.recv(1024).decode()

    print("Server replied:", data)

    if msg.lower() == "exit":
        break
        
client.close()

## OUPUT

<img width="431" height="155" alt="image" src="https://github.com/user-attachments/assets/0392b840-af0f-429c-a581-c04c57aa4857" />

<img width="440" height="173" alt="image" src="https://github.com/user-attachments/assets/460340d4-3d9b-4aef-a4c4-88917e0803c3" />


## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
