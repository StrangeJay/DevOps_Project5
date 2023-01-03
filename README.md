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

Let's take a 
















