
## Reliability

Reliability is one of the most important **Non-Functional Requirements** in System Design.

It tells us whether a system **consistently produces the correct result**, even when failures occur.

---

<h2>Why Do We Need Reliability?</h2>

Suppose you transfer **₹10,000** to your friend using Google Pay.

You click **Send**.

The app says:

```text
Payment Successful ✅
```

But...

- Your friend never receives the money.
- The money is deducted twice.

Would you trust that app again?

❌ No.

The app was **available** (it opened and accepted your request), but it was **not reliable** because it produced the wrong result.

---

<h2>Definition</h2>

> **Definition : Reliability is the ability of a system to consistently perform its intended function correctly, even in the presence of failures.**

Simply:

> **Reliability = Does the system always produce the correct result?**

---

<h2>Real-Life Analogy</h2>

Imagine a calculator.

You type:

```text
2 + 2
```

It returns:

```text
4
```

Perfect.

Now imagine sometimes it returns:

```text
5
```

The calculator is working (available), but you can't trust it.

It is **not reliable**.

---

<h2>Software Example</h2>

Imagine WhatsApp.

You send:

```text
Hello
```

Expected:

```text
Receiver gets "Hello"
```

Instead:

- Message disappears ❌
- Delivered twice ❌
- Corrupted ❌

WhatsApp is running, but the feature isn't behaving correctly.

That's a **reliability problem**.

---

<h2>Availability vs Reliability</h2>

This is one of the favorite interview questions.

| Availability | Reliability |
|--------------|-------------|
| Is the system running? | Is the system producing correct results? |
| Focuses on uptime | Focuses on correctness |
| "Can I use it?" | "Can I trust it?" |
| Measured by uptime % | Measured by correct operation, error rates, data integrity |

---

<h2>Examples</h2>

### Gmail

Server is running.

You can login.

You can open Inbox.

Everything works.

**Availability**

✅ High

Now imagine every email disappears after **5 minutes**.

Availability?

✅ Yes

Reliability?

❌ No

---

### Amazon

Website opens.

You can search.

You can buy.

But every payment is charged twice.

Availability?

✅ Yes

Reliability?

❌ No

---

### Hospital Software

Doctors can open the application.

But patient records show incorrect information.

Availability?

✅ High

Reliability?

❌ Extremely poor

---

<h2>Why Reliability Matters</h2>

Some applications cannot tolerate incorrect results.

Examples:

### Banking

If **₹1000 becomes ₹10,000** by mistake...

Huge problem.

---

### Hospital

Wrong patient report...

Can risk lives.

---

### Airline

Wrong passenger list...

Major operational issue.

---

### Stock Market

Wrong share price...

Can cause massive financial losses.

---

<h2>Characteristics of a Reliable System</h2>

A reliable system should:

- ✅ Return correct results
- ✅ Not lose data
- ✅ Avoid duplicate operations
- ✅ Recover from failures
- ✅ Be consistent

---

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

---

### 2. Database Failure

Data gets corrupted.

---

### 3. Network Failure

Request reaches server.

Response never reaches user.

The client retries.

Payment gets processed twice.

---

### 4. Hardware Failure

Disk crashes.

Data lost.

---

### 5. Human Error

- Wrong deployment
- Wrong configuration
- Accidental database deletion

---

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

---

### 2. Backups

- Daily backups
- Weekly backups
- Cloud backups

If something is deleted,

restore it.

---

### 3. Testing

- Unit Testing
- Integration Testing
- Load Testing
- Regression Testing

Catch bugs before production.

---

### 4. Monitoring

Detect failures quickly.

Example:

```text
CPU reaches 100%
```

Alert the engineering team.

---

### 5. Retry Mechanisms

If a network request fails,

retry safely.

---

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

---

<h2>Real Company Examples</h2>

### Google

Stores multiple copies of data.

If one machine dies,

others continue.

---

### Amazon

Orders are stored in multiple systems.

Backups exist.

Transactions are protected.

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

Reliability?

✅ High

Availability?

❌ Low

---

<h2>Can a System Be Available but Not Reliable?</h2>

Yes.

Website opens.

Users login.

Payments fail.

Messages disappear.

Wrong results.

Availability?

✅ High

Reliability?

❌ Low

---

<h2>Memory Trick</h2>

Imagine a restaurant.

**Availability**

> Restaurant is open.

You can enter.

**Reliability**

> Did you receive the correct food?

Ordered:

```text
Pizza
```

Received:

```text
Pizza
```

Reliable.

Received:

```text
Burger
```

Not reliable.

---

<h2>Interview Questions</h2>

### Q1. What is Reliability?

**Answer:**

Reliability is the ability of a system to consistently produce correct results, even when failures occur.

---

### Q2. What is the difference between Availability and Reliability?

| Availability | Reliability |
|--------------|-------------|
| Is the service accessible? | Are the results correct? |
| Focuses on uptime | Focuses on correctness |
| Can I use it? | Can I trust it? |

---

### Q3. Can a system be reliable but not available?

✅ Yes.

Example:

A payment system always processes transactions correctly but is down for two hours.

---

### Q4. Can a system be available but not reliable?

✅ Yes.

Example:

A website is online, but payments are processed incorrectly.

---

### Q5. How can companies improve reliability?

- Replication
- Backups
- Testing
- Monitoring
- Retry Mechanisms
- Idempotency

---

<h2>Key Takeaways</h2>

- **Reliability = Producing correct results consistently.**
- Reliability focuses on **correctness**, not uptime.
- A system can be **available but not reliable.**
- A system can be **reliable but not available.**
- Reliable systems avoid data loss, duplicate operations, and incorrect results.
- Companies improve reliability using **Replication, Backups, Testing, Monitoring, Retry Mechanisms, and Idempotency.**
