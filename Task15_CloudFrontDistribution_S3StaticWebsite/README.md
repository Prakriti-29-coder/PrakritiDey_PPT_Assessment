# Task 15: CloudFront Distribution for S3 Static Website

## Objective
To configure a Content Delivery Network (CDN) using Amazon CloudFront in front of an Amazon S3 static website to improve performance, security, and global content delivery.

---

## Services Used

- Amazon Web Services (AWS)
- Amazon S3
- Amazon CloudFront

---

## Architecture

User → CloudFront → S3 Static Website

CloudFront caches website content at edge locations worldwide and delivers it over HTTPS for faster and secure access.

---

## Implementation Steps

### Step 1: Create S3 Bucket
- Created bucket: `my-static-website-unique123`
- Selected region: us-east-1
- Disabled "Block all public access"

---

### Step 2: Enable Static Website Hosting
- Enabled Static Website Hosting
- Index document: `index.html`
- Error document: `error.html`

---

### Step 3: Upload Website Files
Uploaded the following files:
- index.html
- error.html

---

### Step 4: Configure Bucket Policy

Added the following policy to allow public read access:

{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadAccess",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::my-static-website-unique123/*"
        }
    ]
}

---

### Step 5: Create CloudFront Distribution

- Distribution type: Single website or app
- Origin domain: `my-static-website-unique123.s3-website-us-east-1.amazonaws.com`
- Origin type: Custom Origin
- Viewer protocol policy: Redirect HTTP to HTTPS
- Default root object: `index.html`
- Used default CloudFront certificate
- Waited until status changed to **Deployed**

---

## Output

The static website was successfully accessed using the CloudFront domain URL:

https://d3un5bd68trbcz.cloudfront.net/

The website is now delivered globally using CloudFront CDN with HTTPS enabled.

---

## Learning Outcomes

- Understood CDN concept
- Learned difference between S3 REST endpoint and S3 Website endpoint
- Configured CloudFront with S3 origin
- Implemented HTTPS redirection
- Improved global website performance using edge caching
