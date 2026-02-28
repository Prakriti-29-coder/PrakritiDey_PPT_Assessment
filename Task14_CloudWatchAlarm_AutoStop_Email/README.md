# Task 14: CloudWatch Alarm (70% CPU → Auto Stop + Email)

## Objective
To configure automated monitoring using Amazon CloudWatch so that when EC2 CPU utilization exceeds 70%, the instance is automatically stopped and an email notification is sent.

---

## Services Used
- Amazon EC2
- Amazon CloudWatch
- Amazon SNS (Simple Notification Service)

---

## Architecture
EC2 Instance → CloudWatch monitors CPU →  
If CPU > 70% →  
1. Send Email via SNS  
2. Stop EC2 Instance Automatically  

---

## Step 1: Create SNS Topic

1. Open SNS Console.
2. Click **Create Topic**.
3. Type: Standard
4. Topic Name: `HighCPUAlertTopic`
5. Click Create.

### Create Subscription:
- Protocol: Email
- Endpoint: Your email address
- Confirm subscription from email inbox.

---

## Step 2: Create CloudWatch Alarm

1. Open CloudWatch Console.
2. Go to **Alarms → Create Alarm**.
3. Select Metric:
   - EC2 → Per-Instance Metrics
   - Choose your EC2 instance
   - Select **CPUUtilization**

4. Configure Conditions:
   - Threshold Type: Static
   - Condition: Greater than
   - Threshold Value: 70
   - Period: 1 minute
   - Evaluation Periods: 1
   - Datapoints to alarm: 1

5. Configure Actions:
   - When in ALARM:
     - Send notification to SNS topic `HighCPUAlertTopic`
     - EC2 Action → Stop this instance

6. Name the alarm:
   - Alarm Name: `HighCPUStopAlarm`

7. Click Create Alarm.

---

## Step 3: Testing the Alarm

Connected to EC2 instance and installed stress tool.

For Ubuntu:sudo apt install stress -y

This increased CPU utilization above 70%.

---

## Result

When CPU usage exceeded 70%:

- CloudWatch Alarm state changed to **ALARM**
- Email notification received via SNS
- EC2 instance automatically changed from:
  Running → Stopping → Stopped

## Conclusion

Successfully implemented automated monitoring and action using CloudWatch Alarm.

When CPU utilization exceeded 70%, the system automatically:
- Sent an email alert
- Stopped the EC2 instance

This demonstrates monitoring, alerting, and automated response in AWS.
