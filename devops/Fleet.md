# DevOps Challenge 1

Write a program such that:

Given an id_rsa.pub file via an environment variable named “PICUS_PUBKEY”, user of this program:

1. Given a CustomerId and a NodeType, it should be able to create an ec2 instance (see Node Properties) and return a NodeId

    ```
    $ foo create --customer-id “a11f4af4b693” --node-type “Manager”
    i-9b7891db92fdda53f
    ```

1. Given a CustomerId, it should be able to list all the NodeIds belonging to a specific CustomerId

    ```
    $ foo list-nodes --customer-id “a11f4af4b693”
    i-9b7891db92fdda53f
    i-8aa344f8c2fa2983c
    ```

1. It should be able to list all NodeIds, CustomerIds and their corresponding IPs (ex: to execute a specific command on all nodes)

    ```
    $ foo list-all
    a11f4af4b693, i-9b7891db92fdda53f, 34.32.55.11
    a11f4af4b693, i-8aa344f8c2fa2983c, 45.44.23.39
    ```

1. Given a selector (CustomerId and/or a NodeType) and an absolute file path, it should be able to execute a script on all nodes saving each execution’s stdout and stderr to some medium

    ```
    $ foo execute --customer-id “a11f4af4b693” --script /home/sysop/updatePackages.sh
    $ foo execute --node-type “Manager” --script /home/sysop/genReport.sh
    ```

1. Should be able to snapshot a specific Node’s ‘/data’ mount point

    ```
    $ foo backup --node-id “i-9b7891db92fdda53f”
    i-913749823749211
    ```

1. Should be able to list backups of a specific node along with the snapshot date

    ```
    $ foo list-backups --node-id “i-9b7891db92fdda53f”
    i-913749823749211, 2017-03-20 21:19
    i-913749823749233, 2017-02-21 07:30
    ```

1. Should be able to roll-back to a specific BackupId for a given NodeId

    ```
    $ foo rollback --backup-id “i-913749823749211”
    ```

# Appendix:

* Types involved:

| Name        | Type   | Constraint          |
| ------------|--------|---------------------|
| CustomerId  | String |                     |
| NodeType    | String | `Manager` or `Peer` |
| BackupId    | String |                     |
| NodeId      | String |                     | 

* Node Properties:

| Node Type | Property    | Value     |
|-----------|-------------|----------:|
| Manager   | Disk Size   |  20 GB    |
|           | Memory      |   4 GB    |
|           | Mount Point |  10 GB    |
| Peer      | Disk Size   |  10 GB    |
|           | Memory      |   1 GB    |

