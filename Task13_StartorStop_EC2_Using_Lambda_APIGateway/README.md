# Task 13: Start/Stop EC2 using Lambda + API Gateway

## Objective
Automate starting and stopping an EC2 instance using a serverless Lambda function triggered by API Gateway. This demonstrates serverless automation and API-based cloud control.

---

## Steps

### 1. IAM Role
- Created a role `LambdaEC2ControlRole` for Lambda.
- Attached the following policies:
  - `AmazonEC2FullAccess` → to allow starting/stopping EC2 instances.
  - `AWSLambdaBasicExecutionRole` → to allow logging to CloudWatch.

---

### 2. Lambda Function
- Created Lambda function `EC2ControlLambda` (Python 3.14).
- Function reads the query parameter `action` from the API request:
  - `?action=start` → starts the EC2 instance.
  - `?action=stop` → stops the EC2 instance.
- Lambda code snippet:

```python
import json
import boto3

ec2 = boto3.client('ec2')
INSTANCE_ID = 'i-06da1d9086e49252e'  # Replace with your EC2 ID

def lambda_handler(event, context):
    action = event.get('queryStringParameters', {}).get('action', '').lower()
    
    if action == 'start':
        ec2.start_instances(InstanceIds=[INSTANCE_ID])
        return {'statusCode': 200, 'body': json.dumps(f'EC2 instance {INSTANCE_ID} is starting.')}
    elif action == 'stop':
        ec2.stop_instances(InstanceIds=[INSTANCE_ID])
        return {'statusCode': 200, 'body': json.dumps(f'EC2 instance {INSTANCE_ID} is stopping.')}
    else:
        return {'statusCode': 400, 'body': json.dumps('Invalid action. Use ?action=start or ?action=stop')}
