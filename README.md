## SHREE LEKHA.S 212223110052
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
```
server.py

import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM) 
s.bind(('localhost', 8000)) 
s.listen(5) 
print("Server listening on port 8000...")
while True:
    c, addr = s.accept()  
    print("Connected to", addr)
    while True:
        client_message = c.recv(1024).decode()  
        if not client_message or client_message.lower() == 'exit': 
            break
        print("Received message:", client_message)

        c.sendall(client_message.encode()) 
    print("Connection closed.")
    c.close() 



client.py

import socket
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)  
s.connect(('localhost', 8000))  
while True:
    msg = input("Client > ") 
    s.send(msg.encode()) 
    if msg.lower() == 'exit':
        break
    print("Server > ", s.recv(1024).decode()) 
s.close()  # Close the connection

```
## PROGRAM:
![Screenshot 2024-04-12 093211](https://github.com/SHREELEKHAS/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/149![Screenshot 2024-04-12 093518](https://github.com/SHREELEKHAS/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/149768910/3dfb5fc6-f779-45b7-aaef-56529ec22132)
768910/8dde6a80-69ee-4b60-b0f7-2586b8c63241)


## OUTPUT
![Screenshot 2024-04-12 093642](https://github.com/SHREELEKHAS/3a.Sockets_Creation_for_Echo_Client_and_Echo_Server/assets/149768910/282cd3a2-29b1-41cb-9005-bdf877c4a8ff)

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
