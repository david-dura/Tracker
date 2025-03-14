# Project: Cloud-Based Job Application Tracker API
A REST API built with C# and ASP.NET Core, leveraging AWS services and following SOLID principles with unit tests. Terraform will manage the infrastructure.

### Project Overview

This API allows users to track job applications, store resumes securely, receive notifications about status updates, and handle background processing efficiently.

### Tech Stack & AWS Services

+ __Backend__: ASP.NET Core Web API
+ __Database__: Amazon RDS (PostgreSQL/MySQL)
+ __Authentication__: AWS Cognito (or JWT-based authentication)
+ __File Storage__: AWS S3 (to store resumes)
+ __Secret Management__: AWS Secrets Manager (for API keys, DB credentials)
+ __Background Processing__: AWS SQS (to queue tasks for async processing)
+ __Notifications__: AWS SNS (email/SMS notifications for status changes)
+ __Serverless Functions__: AWS Lambda (to process queued messages asynchronously)
+ __Infrastructure as Code__: Terraform (to provision AWS resources)

#### Core Features & AWS Integration

1. User Authentication & Authorization
    - Users register/login via AWS Cognito or JWT.
    - Role-based access control for admins & users.

2. Job Application Management
    - Users can Create, Read, Update, Delete (CRUD) job applications.
    - Each application includes position, company, status, and a resume.

3. Resume Upload & Retrieval (AWS S3)
    - Users upload their resumes as PDFs.
    - Files are securely stored in AWS S3.
    - Secure URL generation for downloading resumes.

4. Secure Secrets Management (AWS Secrets Manager)
    - Store DB credentials, API keys securely.
    - Fetch secrets at runtime in the app.

5. Background Processing for Email Notifications (AWS SQS + Lambda + SNS)
    - Users receive status change notifications via email/SMS.
    - Job application updates trigger an SQS message.
    - An AWS Lambda function processes messages from SQS.
    - SNS sends email/SMS alerts to the user.
