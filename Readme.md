# sFTP Take-Home Challenge 

This is a technical challenge for a DevOps Engineer position. 

## Description
- Part 1: Setup an sFTP server on AWS and connect it to an S3 bucket 
- Part 2: Write an IaC template for CloudFormation to automate the setup of the sFTP server for future clients. 

## Part1: Steps to connect to the server and read/write.

|  username    |  server| Key |
|  ---         |  ---   | --- |
|  realblocks1 | s-48ae3408abc74391b.server.transfer.us-east-1.amazonaws.com | sftp-key|
 

### 1.1 Connect to the server (OpenSSH): 

```bash
sftp -i sftp-key realblocks1@s-48ae3408abc74391b.server.transfer.us-east-1.amazonaws.com
```

### 1.2 Get files (Download):

The server has 2 files (at the time of writing this): test1.txt and test2.txt.  
For example **test1.txt** was used here:

```
get test1.txt
```

### 1.3 Write files (Upload):
The file test3.txt on my local machine and was used: 

```
put test3.txt 
```

## Part2: CloudFormation template 

The YAML file defines two resources:  
1- The sFTP server.  
2- A user for the sFTP server.  