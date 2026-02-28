# S3 Upload Email Notification (Lambda + SNS)

## Objective
Trigger an email notification whenever a file is uploaded to an S3 bucket using AWS Lambda and SNS.

## Steps

1. **Create S3 Bucket**
   - Go to AWS S3 → Create bucket → Name it uniquely → Click Create.

2. **Create SNS Topic**
   - Go to AWS SNS → Create topic → Name: `S3UploadNotifications`.
   - Create email subscription → Confirm in email.

3. **Create Lambda Function**
   - Go to AWS Lambda → Create function → Runtime Python 3.11.
   - Add the Lambda code provided.
   - Replace SNS_TOPIC_ARN with your topic ARN.

4. **Add S3 Trigger**
   - Lambda → Configuration → Event sources → Add trigger → S3.
   - Event type: All object create events → Add.

5. **Test**
   - Upload a file to S3 bucket.
   - Check your email for notification.

## Notes
- Ensure SNS subscription is confirmed via email.
- Lambda must have permissions to publish to SNS.
