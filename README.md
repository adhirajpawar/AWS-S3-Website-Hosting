# AWS S3 Website Hosting Project

This project demonstrates how to host a static website using **Amazon S3 (Simple Storage Service)**. Amazon S3 is a scalable, cost-effective, and easy-to-use service for hosting static websites, making it an ideal choice for personal portfolios, documentation sites, or any static web application.

---

## Features

- **Static Website Hosting**: Host HTML, CSS, JavaScript, and other static files directly from an S3 bucket.
- **Cost-Effective**: Pay only for the storage and bandwidth you use.
- **Scalable**: Automatically scales to handle traffic spikes.
- **Secure**: Configure bucket policies and permissions to control access to your website.

---

## Prerequisites

Before getting started, ensure you have the following:
1. An **AWS account**.
2. Basic knowledge of **HTML, CSS, and JavaScript** (for creating the website).
3. The **AWS Management Console** access.

---

## Steps to Host a Website on AWS S3

### 1. Create an S3 Bucket
1. Log in to the **AWS Management Console**.
2. Navigate to the **S3 service**.
3. Click **Create bucket**.
4. Provide a unique bucket name (e.g., `my-static-website`).
5. Choose the region closest to your audience.
6. Enable **Public Access** for the bucket (required for website hosting).
7. Click **Create bucket**.

### 2. Upload Website Files
1. Inside your S3 bucket, click **Upload**.
2. Add your website files (e.g., `index.html`, `style.css`, `script.js`, images, etc.).
3. Set the permissions for each file to **Public Read**.
4. Click **Upload**.

### 3. Enable Static Website Hosting
1. Go to the **Properties** tab of your S3 bucket.
2. Scroll down to **Static website hosting** and click **Edit**.
3. Select **Enable**.
4. Specify the **Index document** (e.g., `index.html`).
5. (Optional) Specify an **Error document** (e.g., `error.html`).
6. Save changes.

### 4. Configure Bucket Policy
1. Go to the **Permissions** tab of your S3 bucket.
2. Under **Bucket Policy**, add the following policy to make the bucket publicly accessible:
   ```json
   {
     "Version": "2012-10-17",
     "Statement": [
       {
         "Sid": "PublicReadGetObject",
         "Effect": "Allow",
         "Principal": "*",
         "Action": "s3:GetObject",
         "Resource": "arn:aws:s3:::your-bucket-name/*"
       }
     ]
   }
