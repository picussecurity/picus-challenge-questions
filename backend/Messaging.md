# Simple messaging app

Implement a 1-1 messaging app. Server runs first, client connects to the server.
Server side should take port number to listen as command line argument. Client
side should take server's IP address and port number as command line arguments.
Receiving side sends an ack message to the sender. Wire protocol should not make
any assumptions on data format (encoding etc.) and size (e.g. `cat binary_file |
client` should just work). UI is your choice (command line, GTK gui, web UI
etc.).
