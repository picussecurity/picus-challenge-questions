# Client Server Architecture

## Problem Description
Please write an application which will collect information from its
clients and provide querying capabilities. The server must meet the
following requirements:

1. It should work as a command-line application implementing these
   commands a. list-clients: It should print the list of registered
   clients b. show-messages <start_date> <end-date>: It should print
   received messages within the specified times

2. It should listen to a TCP for client registrations and responses,
   and persist these

3. It should periodically send a request to the registered clients and
   wait for a response. These requests should be read from a CSV
   file. The requests can be:

   a. Operating system info

   b. Disk space and free space info

   c. .NET framework version info

The client must meet the following requirements:

1. Should send a register message to the server.

2. Should process the messages sent from the server and respond
   accordingly.

## Types:

### CSV rows:

|Name|Type  |
|--|--|
|MessageId|int|
|Name|string|
|MessageType|string|
|Parameters|string|

### Messge responses:

ResultMessage:
|Field|Type|Value|
|--|--|--|
|MessageId|int||
|MessageType|string||
|Status|int|0=Completed, 1=Uncompleted|
|Result|String||

DiskMessage: 
|Field|Type|Value|
|--|--|--|
|MessageId|int||
|MessageType|string||
|Status|int|0=Completed, 1=Uncompleted|
|Result|string||
|Capacity|long||
|FreeSpace|long||

SystemMessage: 
|Field|Type|Value|
|--|--|--|
|MessageId|int||
|MessageType|string||
|Status|int|0=Completed, 1=Uncompleted|
|Result|string||
|WindowsEdition|string||
|ArchitectureType|string||
|OSVersion|string||

FrameworkMessage: 
|Field|Type|Value|
|--|--|--|
|MessageId|int||
|MessageType|string||
|Status|int|0=Completed, 1=Uncompleted|
|Result|string||
|FrameworkVersion|string||

### Sample CSV:
```
MessageId,Name,MessageType,Parameters
1,Disk capacity check.,DiskMessage,C
2,Disk capacity check.,DiskMessage,D
3,System information check.,SystemMessage,
4,Framework version check.,FrameworkMessage,
```
