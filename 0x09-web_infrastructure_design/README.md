# 0x09. Web Infrastructure Design

## Overview
This project is about designing and explaining a simple one-server web infrastructure.  
It covers the basic components of a web stack, how they interact, and potential issues such as single points of failure (SPOF) and scalability limits.

The design is based on:
- **1 Server** (Ubuntu)
- **1 Web server** (Nginx)
- **1 Application server**
- **Application files** (codebase)
- **1 Database** (MySQL)
- **1 Domain name** (`foobar.com`) with a `www` DNS record pointing to the server IP (`8.8.8.8`)

---

## Diagram
![Simple Web Stack](https://i.imgur.com/SVA1Qgn.jpeg)

---

## Components and Roles

### 1. Server
A server is a physical or virtual machine that hosts and runs the web infrastructure.  
It stores files, runs services, and processes requests from users.

### 2. Domain Name
A domain name is the human-readable address of a website.  
Example: `www.foobar.com` makes it easier for users to access the site without remembering the IP address.

### 3. DNS Record
- The `www` in `www.foobar.com` is a **CNAME** or **A record** (in this case pointing to IP `8.8.8.8`).
- It tells the DNS where the domain should direct traffic.

### 4. Web Server (Nginx)
The web server handles HTTP(S) requests from the client and serves static files (HTML, CSS, images) or forwards dynamic requests to the application server.

### 5. Application Server
The application server runs the back-end application logic.  
It processes dynamic content requests, interacts with the database, and returns processed results to the web server.

### 6. Application Files
The codebase that contains the website or application logic (HTML, CSS, JavaScript, server-side code like PHP, Python, or Node.js).

### 7. Database (MySQL)
Stores and manages data for the application (user data, posts, transactions, etc.).

### 8. Communication
The server communicates with the user’s browser via **HTTP** or **HTTPS** over the internet.

---

## Issues with This Infrastructure

1. **Single Point of Failure (SPOF)**  
   If the server goes down, the entire website is unavailable.

2. **Downtime During Maintenance**  
   Updating the application or restarting the server causes temporary downtime.

3. **Scalability Limits**  
   A single server cannot handle a large amount of incoming traffic efficiently.

---

## Acronyms to Know
- **LAMP**: Linux, Apache/Nginx, MySQL, PHP/Python/Perl  
- **SPOF**: Single Point of Failure  
- **QPS**: Queries Per Second (measure of load on a system)

---

## Author
This project is part of the **ALX System Engineering & DevOps** curriculum.
