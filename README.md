# CLIENT-SERVER ARCHITECTURE WITH MYSQL   
Understanding Client-Server Architecture  

[Client-Server Architecture](https://en.wikipedia.org/wiki/Client%E2%80%93server_model) is a concept you will encounter in many areas of your IT journey. Client-Server refers to an architecture in which two or more computers are connected together over a network to send and receive requests between one another. In their communication, each machine has its own role: the machine sending requests is usually referred to as "Client" and the machine responding (serving) is called "Server".  

A simple diagram of Web Client-Server architecture is presented below:  
![Screenshot_20230103_211319](https://user-images.githubusercontent.com/105195327/210434114-0881fda9-b27c-4893-bcaf-a49bc8406a70.png)  
  
![Screenshot_20230103_211440](https://user-images.githubusercontent.com/105195327/210434241-b1a2133c-fa8e-48b3-b342-99d33d3adf70.png)  

In the example above, a machine that is trying to access a Web site using a Web browser or simply ‘curl’ command is a client and it sends HTTP requests to a Web server (Apache, Nginx, IIS or any other) over the Internet. 
If we extend this concept further and add a Database Server to our architecture, we can get this picture:   

![Screenshot_20230103_211616](https://user-images.githubusercontent.com/105195327/210434440-bc020ef3-4c7d-47b5-8001-a390fbc885ad.png)  

In this case, our Web Server has the role of a "Client" that connects and reads/writes to/from a Database (DB) Server (MySQL, MongoDB, Oracle, SQL Server or any other), and the communication between them happens over a Local Network. 
> **Note** It can also be an Internet connection, but it is a common practice to place Web Server and DB Server close to each other in a local network.  

The setup on the diagram above is a typical generic Web Stack architecture that you have already implemented in previous projects (LAMP, LEMP, MEAN, MERN), this architecture can be implemented with many other technologies (various Web and DB servers), from small [Single-page applications](https://en.wikipedia.org/wiki/Single-page_application) to large and complex portals.  

### A real example of a LAMP website  
In [**Project 1**](https://github.com/StrangeJay/DevOps_Journey) you implemented a **LAMP STACK** website, let us take an example of a commercially deployed LAMP website – $\color{pink}{www\ .propitixhomes\ .com}$  

This LAMP website server(s) can be located anywhere in the world and you can reach it also from any part of the globe over global network. 
Assuming you type in $\color{pink}{www\ .propitixhomes\ .com}$ on your browser, it means your browser is considered the **"Client".** It is sending requests to the remote server, and is expecting a response from the remote server.  

Let's take a very quick example and see Client-Server communication in action.  

- Open up your Ubuntu or Windows terminal and run the curl command:
> curl -Iv www.propitixhomes.com   

> **Note** If your Ubuntu does not have 'curl' you can install it by running `sudo apt install curl`

In this example, your terminal will be the **client**, while $\color{pink}{www\ .facebook\ .com}$ will be the **server.**   

See the response from the remote server in the below output. You can also see that the requests from the URL are being served by a computer with an IP address 31.13.83.36 on port 80. *More on IP addresses and ports when we get to Networking related projects*  

![Screenshot_20230103_224903](https://user-images.githubusercontent.com/105195327/210447082-251f186a-d786-4daa-aedc-029b4d4fd612.png)  
Another way to get a server’s IP address is to use a simple diagnostic tool like **‘ping’**, it will also show round-trip time – time for packets to go to and back from the server, this tool uses [ICMP protocol](https://en.wikipedia.org/wiki/Internet_Control_Message_Protocol).  


### Side Self Study  
1. Read about [ping](https://en.wikipedia.org/wiki/Ping_(networking_utility)) and [traceroute](https://en.wikipedia.org/wiki/Traceroute) network diagnostic utilities. Be able to make sense of the results of using these tools.  

2. Refresh your knowledge of [basic SQL commands](https://www.w3schools.com/sql/), and be able to perform simple SHOW, CREATE, DROP, SELECT and INSERT SQL queries.   

---

# IMPLEMENT A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM (DBMS).  

## TASK – Implement a Client-Server Architecture using MySQL Database Management System (DBMS).  

To demonstrate a basic client-server using MySQL Relational Database Management System (RDBMS), follow the instructions below:  

- Create and configure two Linux-based virtual servers (EC2 instances in AWS).  
> Server A name - `mysql_server`  
> Server B name - `mysql_client`  

- On $\color{pink}{mysql\ server}$ Linux Server install MySQL **Server** 
Refer to [project2](https://github.com/StrangeJay/DevOps-Project2) if you've forgotten how to do this.     

- On $\color{pink}{mysql\ client}$ Linux Server install MySQL **Client** software.  

- By default, both of your EC2 virtual servers are located in the same local virtual network, so they can communicate with each other using local IP addresses. Use mysql server's local IP address to connect from mysql client. MySQL server uses TCP port 3306 by default, so you will have to open it by creating a new entry in ‘Inbound rules’ in ‘mysql server’ Security Groups. For extra security, do not allow all IP addresses to reach your ‘mysql server’ – allow access only to the specific local IP address of your ‘mysql client’.   

- You might need to configure MySQL server to allow connections from remote hosts.  
> sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf  

Replace ‘127.0.0.1’ to ‘0.0.0.0’ like this:  
![bind address mysql](https://user-images.githubusercontent.com/105195327/210453444-3f9e23c3-bec1-446b-b49f-52d643f88d13.png)   


















