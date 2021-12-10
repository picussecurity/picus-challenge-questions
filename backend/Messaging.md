# Simple messaging app

## First Part

We want you to implement a 1-1 messaging app over TCP/IP. There will be a server, which acts as a broker between clients, and any number of clients.

The server runs first and takes a port number to listen as a command-line argument. Clients take the nickname, server's IP address, and port number as command-line arguments then connect to the server. After the initial connection, clients can list currently connected clients, and the server responds with nicknames of currently connected users. Then, clients can send messages to any client by specifying the target's nickname. If the GUI is command-line the first word of the message can be the target's nickname, for example. Any syntax or method is accepted as long as it works.

Wire protocol should not make any assumptions on data format (encoding etc.) and size. You can use any kind of UI (command line, GTK GUI, Swing, web UI etc.).

## Second Part

The server should be storing all messages in a persistent medium with sender and recipient nicknames. The storage medium can be a file, DBMS, or anything else you prefer.

A client can also query these messages from the server with a special message sent to a server (in a format you decide).
There should be 3 filters that users can apply:
- Query last x messages
- Query messages that contain some text
- Query according to message direction (sent by me or to me)

Users can use any combination of these filters. Also of course clients should be able to access messages that are sent from or to them. Messages between other clients should not be accessible. If a combination of these queries is used, the `last x messages` query should act like a limiter (similar to `limit` in SQL). Namely, it should not apply other filters on last x messages.

## Submission

Please provide us a `Readme` to help us execute the implementation and query commands you designed. You can assume we will execute this code on a Linux machine with nothing installed.

## Evaluation

We will not evaluate this task in a black-box manner. Therefore, if there are any unclear points to you, you can just write your assumption in a comment and implement accordingly.

Good luck!
