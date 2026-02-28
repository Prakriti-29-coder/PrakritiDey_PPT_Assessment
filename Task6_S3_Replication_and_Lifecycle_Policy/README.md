# S3 Replication and Lifecycle Policy

## Objective
Understand S3 versioning, replication, and lifecycle rules for cost optimization and backup.

## Steps Taken
1. Created two S3 buckets:
   - Source: `prakriti-source-bucket`
   - Destination: `prakriti-dest-bucket`
2. Enabled versioning in both buckets.
3. Configured replication rule from source to destination bucket with IAM role.
4. Uploaded test files and verified replication.
5. Configured lifecycle rule in the source bucket:
   - Transition to Standard-IA after 30 days
   - Transition to Glacier after 60 days
   - Expire old versions after 365 days

## Screenshots
- Screenshot 1: Source and destination buckets
- Screenshot 2: Replication rule configuration
- Screenshot 3: Lifecycle rule configuration
