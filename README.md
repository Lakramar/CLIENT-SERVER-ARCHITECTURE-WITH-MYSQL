# CLIENT-SERVER ARCHITECTURE WITH MYSQL
### Understanding Client-Server Architecture

###### Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another.

###### In their communication, each machine has its own role: the machine sending requests is usually referred as "Client" and the machine responding (serving) is called "Server".

###### A simple diagram of Web Client-Server architecture is presented below:

![GitHub Dark ](https://darey.io/wp-content/uploads/2021/07/Client-server.png#gh-dark-mode-only)
###### In the example above, a machine that is trying to access a Web site using Web browser or simply ‘curl’ command is a client and it sends HTTP requests to a Web server (Apache, Nginx, IIS or any other) over the Internet.If we extend this concept further and add a Database Server to our architecture, we can get this picture:
###### If we extend this concept further and add a Database Server to our architecture, we can get this picture:
![GitHub Dark ](https://darey.io/wp-content/uploads/2021/07/Client-server2.png#gh-dark-mode-only)

### IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).

###### 1.  Create and configure two Linux-based virtual servers (EC2 instances in AWS).

###### Server A name - `mysql server`
###### Server B name - `mysql client`


###### 2.  On mysql server Linux Server install MySQL Server software.

Interesting fact: MySQL is an open-source relational database management system. Its name is a combination of "My", the name of co-founder Michael Widenius’s daughter, 
and "SQL", the abbreviation for Structured Query Language.


###### 3.  On mysql client Linux Server install MySQL Client software.

###### 4. By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate to each other using local IP addresses. 
######     Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, 
######     so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, 
######     do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.


###### 5.  You might need to configure MySQL server to allow connections from remote hosts.

###### sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf

###### Replace ‘127.0.0.1’ to ‘0.0.0.0’

###### 6. From mysql client Linux Server connect remotely to mysql server Database Engine without using SSH. You must use the mysql utility to perform this action.

###### sudo mysql -u remote_user -h 172.31.19.233 -p 

###### 7. Check that you have successfully connected to a remote MySQL server and can perform SQL queries:

###### Show databases;


