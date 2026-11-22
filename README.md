# Student Notes Portal (AWS EC2, S3 & Load Balancer)

## Project Objective
Build a simple **Student Notes Portal** using **Amazon EC2**, **Amazon S3**, and an **Application Load Balancer (ALB)**. This web-based application demonstrates how to host a website across two EC2 instances, store study materials in an S3 bucket, and distribute incoming traffic using a load balancer.

---

## Services Used
* **Amazon EC2** – Hosts the web application on two virtual servers.
* **Amazon S3** – Stores and serves PDF documents and images.
* **Application Load Balancer (ALB)** – Distributes incoming traffic across the EC2 instances.

---

## Prerequisites
* Active AWS Account
* Basic Linux commands
* Basic HTML knowledge
* Web browser access
* Fundamental understanding of EC2, S3, and Load Balancers

---

## Project Implementation

### 1. Launch Two EC2 Instances
Created two EC2 instances to host the Student Notes Portal for high availability.

### 2. Install Apache Web Server
Installed and configured the Apache HTTP Server (`httpd` / `apache2`) on both EC2 instances.

### 3. Create a Simple HTML Page
Developed an `index.html` page displaying the Student Notes Portal title and links to study materials stored in S3:

```html
<!DOCTYPE html>
<html>
<head>
  <title>My AWS S3 Project</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background-color: #f2f5f3;
      margin: 30px;
    }
    h1 { color: green; }
    h2 { color: #333; }
    img {
      width: 350px;
      border: 2px solid green;
      border-radius: 10px;
    }
    iframe {
      width: 80%;
      height: 500px;
      border: 2px solid green;
    }
    a { color: blue; }
  </style>
</head>
<body>
  <h1>Welcome to My AWS S3 Website</h1>
  <p>This website is hosted using Amazon S3.</p>

  <h2>Linux Hierarchy Image</h2>
  <img src="https://dhvanimevada1302.s3.ap-south-1.amazonaws.com/Linux+Hierarchy.png" alt="Linux Hierarchy">

  <h2>My PDF Document</h2>
  <iframe src="https://dhvanimevada1302.s3.ap-south-1.amazonaws.com/YOUR-PDF-NAME.pdf"></iframe>
  <p>
    <a href="https://dhvanimevada1302.s3.ap-south-1.amazonaws.com/YOUR-PDF-NAME.pdf" target="_blank">
      View or Download PDF
    </a>
  </p>
</body>
</html>
```

### 4. Create an S3 Bucket & Upload Materials
* Created an Amazon S3 bucket to store student study materials.
* Uploaded PDF documents and images to the bucket and enabled public read access (or configured bucket policies) so the website can load them.
* Added the S3 object URLs into the HTML page.

### 5. Configure Target Group & Application Load Balancer
* **Create Target Group:** Created an EC2 target group and registered both EC2 instances.
* **Create Application Load Balancer:** Configured an ALB to receive incoming HTTP traffic.
* **Connect Instances:** Attached the target group to the ALB and verified that both instances passed health checks.

### 6. Test the Application
Accessed the website using the **Application Load Balancer DNS name** and verified that the page loaded properly and all S3 PDF and image links worked.

---

## Expected Output
* Student Notes Portal website accessible through the Load Balancer DNS.
* Website hosted across two healthy EC2 instances.
* Study materials stored in and served from Amazon S3.
* PDF and image links viewable and downloadable directly from the portal.
* Incoming traffic distributed evenly through the Application Load Balancer.

---

## Project Screenshots
Screenshots of the EC2 instances, S3 bucket, Target Group, and live portal are available in the [`/screenshots`](./screenshots) folder.

---

## Key Learnings
* Launching and configuring Amazon EC2 instances.
* Installing and managing Apache Web Server on Linux.
* Creating S3 buckets, uploading objects, and managing object URLs.
* Configuring EC2 Target Groups and health checks.
* Setting up an Application Load Balancer to distribute web traffic.
