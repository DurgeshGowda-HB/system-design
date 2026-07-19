
## Reliability

Reliability is one of the most important **Non-Functional Requirements** in System Design.

It tells us whether a system **consistently produces the correct result**, even when failures occur.

<h2>Why Do We Need Reliability?</h2>

Suppose you transfer **₹10,000** to your friend using Google Pay.

You click **Send**.

The app says : Payment Successful 

But...

- Your friend never receives the money.
- The money is deducted twice.

Would you trust that app again?
 No.

The app was **available** (it opened and accepted your request), but it was **not reliable** because it produced the wrong result.

<h2>Definition</h2>

> **Definition : Reliability is the ability of a system to consistently perform its intended function correctly, even in the presence of failures.**

Simply:

> **Reliability = Does the system always produce the correct result?**

---

-> Real-Life Analogy

Imagine a calculator.

You type:
2 + 2


It returns:4

Perfect.

Now imagine sometimes it returns:

5

The calculator is working (available), but you can't trust it.

It is **not reliable**.

<h2>Software Example</h2>

Imagine WhatsApp.

You send:
Hello

Expected:
Receiver gets "Hello"

Instead:

- Message disappears 
- Delivered twice 
- Corrupted 

WhatsApp is running, but the feature isn't behaving correctly.

That's a **reliability problem**.

<h2>Availability vs Reliability</h2>

This is one of the favorite interview questions.

| Availability | Reliability |
|--------------|-------------|
| Is the system running? | Is the system producing correct results? |
| Focuses on uptime | Focuses on correctness |
| "Can I use it?" | "Can I trust it?" |
| Measured by uptime % | Measured by correct operation, error rates, data integrity |


<h2>-> Examples</h2>

### Gmail

Server is running.

You can login.

You can open Inbox.

Everything works.

**Availability** : High

Now imagine every email disappears after **5 minutes**.

Availability? :  Yes

Reliability? : No

### Amazon

Website opens.

You can search.

You can buy.

But every payment is charged twice.

Availability? : Yes

Reliability? :  No


<h2>Why Reliability Matters</h2>

Some applications cannot tolerate incorrect results.

Examples:

### Banking

If **₹1000 becomes ₹10,000** by mistake...

Huge problem.

### Hospital

Wrong patient report...

Can risk lives.

### Stock Market

Wrong share price...

Can cause massive financial losses.

<h2>Characteristics of a Reliable System</h2>

A reliable system should:

- ✅ Return correct results
- ✅ Not lose data
- ✅ Avoid duplicate operations
- ✅ Recover from failures
- ✅ Be consistent


<h2>Causes of Poor Reliability</h2>

Many things can reduce reliability.

### 1. Software Bugs

Wrong code.

Example:

```java
balance = balance - amount;
```

Instead of:

```java
balance = balance + amount;
```


### 2. Database Failure

Data gets corrupted.

### 3. Network Failure

Request reaches server.

Response never reaches user.

The client retries.

Payment gets processed twice.

### 4. Hardware Failure

Disk crashes.

Data lost.

### 5. Human Error

- Wrong deployment
- Wrong configuration
- Accidental database deletion

<h2>How Do Companies Improve Reliability?</h2>

### 1. Data Replication

Instead of one copy:

```text
Database
```

Use:

```text
DB1
DB2
DB3
```

If one fails,

others still have the data.



### 2. Backups

- Daily backups
- Weekly backups
- Cloud backups

If something is deleted,

restore it.


### 3. Testing

- Unit Testing
- Integration Testing
- Load Testing
- Regression Testing

Catch bugs before production.

### 4. Monitoring

Detect failures quickly.

Example:

```text
CPU reaches 100%
```

Alert the engineering team.


### 5. Retry Mechanisms

If a network request fails,

retry safely.

### 6. Idempotency

Very important.

Suppose a payment request is sent twice.

Without idempotency:

```text
₹500
 ↓
₹500
 ↓
₹1000 deducted
```

With idempotency:

```text
₹500
 ↓
Duplicate request ignored
 ↓
₹500 deducted only once
```

> We'll study **Idempotency** in detail later.


<h2>Real Company Examples</h2>

### Google

Stores multiple copies of data.

If one machine dies,

others continue.

---


### Netflix

If one server fails,

another continues streaming.

Users rarely notice.

---

<h2>Can a System Be Reliable but Not Available?</h2>

Yes.

Imagine:

A payment system works perfectly.

Every transaction is correct.

But...

The server is down for **two hours**.

Reliability? : High

Availability? : Low


<h2>Can a System Be Available but Not Reliable?</h2>

Yes.

Website opens.

Users login.

Payments fail.

Messages disappear.

Wrong results.

Availability? : High

Reliability? : Low


<h2>Key Takeaways</h2>

- **Reliability = Producing correct results consistently.**
- Reliability focuses on **correctness**, not uptime.
- A system can be **available but not reliable.**
- A system can be **reliable but not available.**
- Reliable systems avoid data loss, duplicate operations, and incorrect results.
- Companies improve reliability using **Replication, Backups, Testing, Monitoring, Retry Mechanisms, and Idempotency.**
