## HTTP & HTTPS

HTTP and HTTPS are the foundation of communication between a **Client** and a **Server**.

Without understanding HTTP, topics like **REST APIs, Load Balancers, Authentication, WebSockets, and Microservices** become much harder to understand.

---

<h2>Why Do We Need HTTP?</h2>

Imagine you open Instagram.

Within a second, you see:

- Feed
- Stories
- Messages
- Notifications

Question:

> **How did your phone ask Instagram's server for this data?**

There needs to be a common language between the client and the server.

That language is **HTTP**.

---

<h2>What is HTTP?</h2>

> **Definition : HTTP (HyperText Transfer Protocol) is the standard protocol used for communication between a client and a server.**

Simply:

> **HTTP = The language that clients and servers use to communicate.**

---

<h2>Communication Flow</h2>

```text
Client (Browser / Mobile App)
            │
      HTTP Request
            ▼
       Web Server
            │
      HTTP Response
            ▼
Client Displays Data
```

---

<h2>HTTP Request & Response</h2>

Whenever you perform an action,

the client sends a **Request**.

Example:

```text
Open Amazon Home Page
        │
        ▼
Server Processes Request
        │
        ▼
Returns Response
```

Response may contain:

- Products
- Images
- HTML
- JSON

Think of it like ordering food.

```text
Customer
    │
  Order
    │
    ▼
Restaurant
    │
  Food
    ▼
Customer
```

Exactly the same idea.

---

<h2>Common HTTP Methods</h2>

These tell the server what action you want to perform.

| Method | Purpose | Example |
|---------|---------|---------|
| GET | Read Data | View Products |
| POST | Create Data | Register User |
| PUT | Replace Existing Data | Update Full Profile |
| PATCH | Update Part of Existing Data | Change Only Email |
| DELETE | Remove Data | Delete Account |

---

<h2>Memory Trick</h2>

```text
GET    → Read

POST   → Create

PUT    → Replace

PATCH  → Modify

DELETE → Remove
```

These five methods are enough for most interviews.

---

<h2>Statelessness (Very Important)</h2>

This is one of the most frequently asked interview concepts.

### What does Stateless mean?

> **Definition : Every HTTP request is independent. The server doesn't automatically remember previous requests.**

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

The second request is treated as completely new.

---

<h2>Why is Stateless Good?</h2>

Because **any server can handle any request.**

Imagine you have three servers.

```text
             Users
               │
      ┌────────┼────────┐
      ▼        ▼        ▼
   Server1  Server2  Server3
```

If one server is busy,

another server can process the request.

This makes **Horizontal Scaling** much easier.

> **System Design Insight:** Statelessness is one of the reasons modern web applications can scale to millions of users.

---

<h2>Then How Does a Website Remember I'm Logged In?</h2>

Good question.

When you log in,

the server gives your browser a **Token** or **Session Identifier**.

Future requests include that token.

```text
Login
   │
Token Received
   │
Future Requests
   │
Token Sent Again
   │
Server Identifies User
```

We'll study **JWT, Sessions, and OAuth** later.

---

<h2>What is HTTPS?</h2>

HTTP has one major problem.

Everything is sent as **Plain Text**.

Someone on the network could read it.

Example:

- Username
- Password
- Credit Card Details

Not safe.

---

<h2>HTTPS Solves This Problem</h2>

> **HTTPS = HTTP + Encryption**

The communication is encrypted before it travels across the network.

```text
Client
   │
Encrypted Data
↓↓↓↓↓↓↓↓↓↓↓↓↓↓
Internet
↓↓↓↓↓↓↓↓↓↓↓↓↓↓
Server
   │
Decrypt Data
```

Even if someone intercepts the traffic,

they cannot easily understand the data.

---

<h2>SSL / TLS (High Level)</h2>

People often ask:

> If HTTPS encrypts data, who performs the encryption?

The answer is:

**TLS (Transport Layer Security)**

(Older name: **SSL**)

TLS:

- Encrypts communication
- Verifies the server's identity using a certificate
- Protects data from tampering

You don't need to know the cryptography for most entry-level interviews.

---

<h2>HTTP vs HTTPS</h2>

| HTTP | HTTPS |
|------|-------|
| Not Encrypted | Encrypted |
| Less Secure | Secure |
| Uses Port 80 | Uses Port 443 |
| Suitable only for non-sensitive traffic | Used for almost all modern websites |

---

<h2>Why HTTPS Matters in System Design?</h2>

Imagine a banking application.

Without HTTPS:

```text
Login Password
      │
   Internet
      │
Anyone Can Read It
```

With HTTPS:

```text
Encrypted Password
        │
     Internet
        │
Only Bank Server Can Decrypt
```

That's why every production application uses **HTTPS**.

---

<h2>Real-World Examples</h2>

### Amazon

Uses HTTPS for:

- Customer Login
- Payments
- Orders

---

### Google

Uses HTTPS for:

- Search
- Gmail
- Google Drive

---

### Netflix

Uses HTTPS for:

- Login
- Streaming Requests
- User Profile

All communication is protected.

---

<h2>Interview Questions</h2>

### Q1. What is HTTP?

**Answer:**

HTTP is a protocol used for communication between clients and servers.

---

### Q2. What is Statelessness?

**Answer:**

Each request is independent, and the server doesn't automatically remember previous requests.

---

### Q3. Why is Statelessness useful?

**Answer:**

It makes applications easier to scale because **any server can process any request**.

---

### Q4. Difference between HTTP and HTTPS?

| HTTP | HTTPS |
|------|-------|
| Plain Text Communication | Encrypted Communication |
| Less Secure | Secure |
| Uses Port 80 | Uses Port 443 |
| No TLS | Uses TLS |

---

### Q5. Why do modern websites use HTTPS?

**Answer:**

To protect sensitive information such as:

- Passwords
- Payment Details
- Personal Data

from interception or tampering.

---

<h2>Quick Revision</h2>

```text
HTTP
   │
Communication between Client & Server
   │
Request → Response
   │
Stateless
   │
Easy to Scale
   │
HTTPS
   │
Encrypted Communication
   │
Uses TLS
   │
Secure
```

---

<h2>Memory Trick</h2>

Think of sending a letter.

> **HTTP = Sending an open postcard.**

Anyone who sees it can read the message.

> **HTTPS = Sending a sealed envelope.**

Only the intended receiver can open and read it.

---

<h2>Key Takeaways</h2>

- **HTTP = Communication protocol between Client and Server.**
- HTTP follows the **Request–Response** model.
- HTTP is **Stateless**, making applications easier to scale.
- **HTTPS = HTTP + TLS Encryption.**
- HTTPS protects passwords, payment details, and personal information.
- HTTP uses **Port 80**, HTTPS uses **Port 443**.
- Modern production applications always use **HTTPS** for secure communication.