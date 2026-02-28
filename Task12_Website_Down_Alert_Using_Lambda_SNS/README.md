# Task 12: Website Down Alert using Lambda + SNS

## Objective
Monitor a website's uptime and automatically send alerts when it goes down.

## Steps

1. **SNS Setup**  
   - Created SNS topic `WebsiteAlertTopic`.  
   - Subscribed my email to receive alerts.

2. **Lambda Setup**  
   - Created Lambda function `WebsiteHealthCheck` (Python 3.9).  
   - Lambda checks website status every 5 minutes.  
   - If the website is down, SNS alert is sent.

3. **EventBridge Schedule**  
   - Created schedule `WebsiteCheckSchedule`.  
   - Rate-based schedule: every 5 minutes.  
   - Target: Lambda `WebsiteHealthCheck`.

4. **Testing**  
   - Tested Lambda with valid and invalid URLs.  
   - Verified CloudWatch logs and SNS email alerts.


