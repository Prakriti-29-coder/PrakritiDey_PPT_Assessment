# Task 17: DynamoDB Table Creation (Basic)

## Project Overview

In this task, I created a NoSQL table using Amazon DynamoDB and inserted sample records into it.  
This task helped me understand the basics of serverless databases and how DynamoDB stores data in JSON format.

---

## Objective

- Learn the fundamentals of NoSQL databases.
- Understand how DynamoDB works as a fully managed, serverless database.
- Create a table and insert sample items.

---

## AWS Service Used

- Amazon DynamoDB

---

## Step 1: Create DynamoDB Table

1. Logged in to AWS Console.
2. Searched for **DynamoDB** in the services.
3. Clicked on **Create table**.
4. Entered the following details:
   - Table name: `StudentsTable`
   - Partition key: `StudentID`
   - Data type: String
5. Selected **On-Demand capacity mode** (default).
6. Clicked **Create table**.
7. Waited until the table status changed to **Active**.

---

## Step 2: Insert Sample Items

After the table was active:

1. Opened `StudentsTable`.
2. Clicked on **Explore table items**.
3. Selected **Create item**.
4. Switched to JSON view.
5. Inserted the records

8. Successfully viewed both records in the table.

---

## Key Learnings

- DynamoDB is a serverless NoSQL database.
- It uses a Partition Key instead of a traditional primary key.
- Data is stored in JSON format.
- No server management is required.
- DynamoDB automatically scales based on demand.

---

## Outcome

Successfully created a DynamoDB table and inserted sample records using AWS Console.  
Gained hands-on experience with NoSQL databases and AWS serverless architecture.
