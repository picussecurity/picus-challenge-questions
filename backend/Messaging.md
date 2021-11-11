# Simple messaging app

## First Part

We want you to implement a 1-1 messaging app over TCP/IP. You need to implement a TCP server and a TCP client.

Server runs first and takes port number to listen as command line argument. Client takes server's IP address and port number as command line arguments.
After the initial connection, both peers can send and receive messages to each other via application UI. Received message should be displayed on the receiving side.

Wire protocol should not make any assumptions on data format (encoding etc.) and size. You can use any kind of UI (command line, GTK gui, Swing, web UI
etc.).

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

## Submission

Please provide us a `Readme` to help us execute your implementation and query commands you designed. You can assume we will 
execute this code on a linux machine.

## Evaluation

We will not evaluate this task in a blackbox manner. Therefore, if there are any unclear points to you, you can just
write your assumption in a comment and implement accordingly.

Good luck!
