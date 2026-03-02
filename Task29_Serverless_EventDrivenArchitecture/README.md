# TASK 5 — Serverless + Event-Driven Architecture (AWS + Azure)

Objective: Implement event-driven serverless architecture using storage triggers, serverless compute, and managed databases.

Workflow:
1. Create AWS S3 bucket `my-event-bucket`.
2. Create AWS Lambda `S3ToDynamoLambda` with IAM role (S3 + DynamoDB access).
3. Configure S3 upload trigger to invoke Lambda.
4. Create AWS DynamoDB table `MyDataTable` (partition key `id`).
5. Upload file to S3 → verify DynamoDB entry and CloudWatch logs.
6. Create Azure Resource Group `myResourceGroup`.
7. Create Azure Storage Account `myeventstorage` → Container `samples-workitems`.
8. Create Azure Function App `BlobToCosmosFunc` (Python 3.12, Consumption) with Blob trigger on `samples-workitems/{name}`.
9. Create Azure Cosmos DB `MyCosmosDB` → Container `MyContainer` (partition key `/id`).
10. Connect Azure Function output to Cosmos DB.
11. Upload file to Blob container → verify Cosmos DB entry and Function logs.

Result: AWS: S3 → Lambda → DynamoDB | Azure: Blob → Function → Cosmos DB. Fully serverless & event-driven.
