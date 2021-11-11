# Simple messaging app

## First Part

We want you to implement a 1-1 messaging app. Server runs first, client connects to the server.
Server side should take port number to listen as command line argument. Client
side should take server's IP address and port number as command line arguments.
Receiving side sends an ack message to the sender. Wire protocol should not make
any assumptions on data format (encoding etc.) and size. UI is your choice (command line, GTK gui, web UI
etc.). After the initial connection, both peers can send and receive messages to each other.

## Second Part

Server should be storing all messages in a persistent medium with sender and recipient IP and 
port info (can be file or database or anything else you prefer). 

Client can also query these messages from server with a special message sent to a server (in a format you decide).
There should be 3 filters that user can apply:
- Query last x messages
- Query messages that contain some text
- Query according to message direction (sent by me or to me)

User can use any combination of these filters. Also of course client should not be able to access messages of other users.

You can assume client IP and port defines identity of a user.


## Evaluation

We will not evaluate this task in a blackbox manner. Therefore, if there are any unclear points to you, you can just
write your assumption in a comment and implement accordingly.

Good luck!
