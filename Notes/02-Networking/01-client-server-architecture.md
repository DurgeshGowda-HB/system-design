## Client-Server Architecture

Client-Server Architecture is the **foundation of every web application**.

Without understanding this, topics like **HTTP, Load Balancer, APIs, WebSockets, and Microservices** won't make much sense.

<h3>Why Do We Need Client-Server Architecture?</h3>

Imagine you open Instagram.

Within a second, you see:

- Stories
- Feed
- Notifications
- Messages

Question:

> **Where did all this data come from?**

Is it stored on your phone?

No.

It comes from Instagram's servers.

<h2>Definition</h2>

> **Definition : Client-Server Architecture is a model where the client requests services or data, and the server processes the request and sends back a response.**

Simply:

> **Client asks. Server answers.**

<img src="/images/client-server-architecture.png" alt="clinet-server-architecture picture" width="80%" height="400">

 Example : 

<h2>Software Example</h2>

You open **YouTube**.

Your phone sends : GET Home Page
The server receives it.

It processes:

- Who is the user?
- What videos should be recommended?
- What ads should be shown?

Then it sends back:

- Videos
- Titles
- Thumbnails

<h2>Basic Architecture</h2>

```text
           Request

Client --------------------> Server

           Response

Client <-------------------- Server
```

This is the basis of almost every application.

<h2>Who is the Client?</h2>

> **Definition : A client is anything that requests data or services.**

Examples:

- Chrome Browser
- Mobile App
- Desktop Application
- Smart TV
- Smart Watch

All of these can act as clients.

<h2>Who is the Server?</h2>

> **Definition : A server is a computer or program that receives requests, processes them, and returns responses.**

Examples:

- Instagram Server
- Netflix Server
- Amazon Server
- WhatsApp Server

<h2>Example</h2>

You search : Laptop


### Step 1

Browser sends request.

```text
Chrome
   │
Search Laptop
```

### Step 2

Amazon Server receives it.

```text
Amazon Server
      │
Search Database
```

### Step 3

Database returns products.

### Step 4

Server sends results.

```text
Laptop List
      │
   Browser
```

<h2>Complete Flow</h2>

```text
Request

Client
   │
   ▼

Server
   │
   ▼

Database
   │
   ▲

Server
   │
   ▲

Client
```

This is how most web applications work.

<h2>Multiple Clients</h2>

One server doesn't serve just one person.

```text
     Phone
    
     Laptop
 
     Tablet
    
     Desktop
    
        │
        ▼

+----------------+
|     Server     |
+----------------+
```

Thousands or even millions of clients can connect to the same server.

---

<h2>Multiple Servers</h2>

Imagine Instagram.

Millions of users.

One server isn't enough.

```text
           Users
              │
              ▼

        Load Balancer

       ┌─────┴─────┐
       ▼           ▼
   Server 1    Server 2
                    │
                    ▼
                Server 3
```

We'll learn about **Load Balancers** later.

---

<h2>Client Doesn't Know Everything</h2>

The client usually doesn't know:

- Where the database is
- How recommendations are generated
- Which server handled the request
- Which cache was used

It only knows:

- "I asked for data."
- "I received data."

---

<h2>Stateless Communication (Preview)</h2>

Most HTTP requests are independent.

Example:

```text
Request 1
    │
Response

----------------

Request 2
    │
Response
```

The server doesn't automatically remember previous requests.

We'll study **Statelessness** in detail when we cover **HTTP**.

---

<h2>Why Use Client-Server Architecture?</h2>

Imagine storing all Instagram data on your phone.

Problems:

- Huge storage requirements
- Data would become outdated
- Other users couldn't see your updates
- Security would be poor

Instead,

Keep the data on centralized servers.

Clients simply request what they need.

---

<h2>Advantages</h2>

### 1. Centralized Data

Everything is stored on the server.

---

### 2. Better Security

Sensitive logic and data stay on the server.

---

### 3. Easy Updates

Update the server once.

Every client benefits.

---

### 4. Easy Maintenance

Fix one backend.

Millions of users get the improvement.

---

<h2>Disadvantages</h2>

### 1. Server Failure

If the server crashes...

Clients can't get data.

---

### 2. Network Dependency

No internet?

No communication.

---

### 3. High Traffic

Millions of clients may overload the server.

That's why we need:

- Load Balancers
- Caching
- Horizontal Scaling

---

<h2>Real-World Examples</h2>

### WhatsApp

**Client**

- Mobile App

**Server**

- Stores messages
- User status
- Media
- Routes messages

---

### Netflix

**Client**

- TV App

**Server**

- Streams videos
- Provides recommendations

---

### Amazon

**Client**

- Website
- Mobile App

**Server**

- Handles search
- Cart
- Orders
- Payments

---

<h2>Interview Questions</h2>

### Q1. What is a Client?

**Answer:**

A program or device that requests data or services.

---

### Q2. What is a Server?

**Answer:**

A program or computer that processes requests and returns responses.

---

### Q3. Can one server handle multiple clients?

✅ Yes.

Thousands or even millions of clients can connect to the same server.

---

### Q4. Can one client communicate with multiple servers?

✅ Yes.

For example, a web page may fetch data from different backend services or content from a CDN.

---

<h2>Memory Trick</h2>

Think of a restaurant.

> **Client = Customer who places the order.**

> **Server = Kitchen that prepares the food.**

> **Response = Food delivered back to the customer.**

The customer requests.

The kitchen processes.

The customer receives the result.

---

<h2>Key Takeaways</h2>

- **Client = Requests data or services.**
- **Server = Processes requests and returns responses.**
- Client and Server communicate using the **Request-Response** model.
- One server can handle **multiple clients**.
- One client can communicate with **multiple servers**.
- Data is stored on the server, not on the client.
- Client-Server Architecture is the foundation of modern web applications.
- Technologies like **HTTP, APIs, Load Balancers, Caching, and Microservices** are built on this architecture.
