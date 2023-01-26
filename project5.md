# PROJECT 5: Client/Server Architecture Using A MySQL Relational Database Management System


- Create and configure two Linux-based virtual servers (EC2 instances in AWS).
```
Server A name - `mysql server`
Server B name - `mysql client`
```
![ec2](./images/02-ec2.PNG)  

- On mysql server Linux Server install MySQL **Server** software.
![server](./images/08-install%20server.PNG)

- On mysql client Linux Server install MySQL __Client__ software.
![client](./images/07-install%20client.PNG)  

By default, both EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses. Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.

- configure MySQL server to allow connections from remote hosts.

```
sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf
```
Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:

![edit](./images/09-vi%20edit.PNG)

- From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.  

Step 1. create mysql user on server  
![user](./images/04-create%20user.PNG)

Step 2. Connect from mysql client
![connect](./images/05-connection%20success.PNG) 


- Check that you have successfully connected to a remote MySQL server and can perform SQL queries:
```
Show databases;
```
![result](./images/06-result.PNG)



Congratulations!