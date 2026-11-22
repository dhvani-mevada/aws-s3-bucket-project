#Project Objective
##Build a simple Student Notes Portal using EC2, S3 Bucket, and Load Balancer.
##The Student Notes Portal is a simple web-based application developed using Amazon Web Services (AWS).

The project demonstrates how to deploy a website on two EC2 instances, store study materials in an Amazon S3 bucket, and distribute incoming traffic using an Application Load Balancer (ALB)

#Services Use
##EC2
##S3 Bucket
##Load Balancer

#Prerequisites
##AWS Account
##Basic Linux commands
##Basic HTML knowledge
##Browser access
##Understanding of EC2, S3 and Load Balancer

#Project Implementation
##Launch Two EC2 Instances: Created two EC2 instances to host the Student Notes Portal.
##Install Apache Web Server: Installed and configured Apache HTTP Server on both EC2 instances.
##Create a Simple HTML Page: Developed an HTML page displaying the Student Notes Portal title and study material links.
''''bash

<!DOCTYPE html>
<html>
<head>
    <title>My AWS S3 Project</title>

    <style>
        body {
            font-family: Arial;
            text-align: center;
            background-color: #f2f5f3;
            margin: 30px;
        }

        h1 {
            color: green;
        }

        h2 {
            color: #333;
        }

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

        a {
            color: blue;
        }
    </style>
</head>

<body>

    <h1>Welcome to My AWS S3 Website</h1>

    <p>This website is hosted using Amazon S3.</p>

    <h2>Linux Hierarchy Image</h2>

    <img src="https://dhvanimevada1302.s3.ap-south-1.amazonaws.com/Linux+Hierarchy.png"
         alt="Linux Hierarchy">

    <h2>My PDF Document</h2>

    <iframe src="https://dhvanimevada1302.s3.ap-south-1.amazonaws.com/YOUR-PDF-NAME.pdf">
    </iframe>

    <p>
        <a href="https://dhvanimevada1302.s3.ap-south-1.amazonaws.com/YOUR-PDF-NAME.pdf"
           target="_blank">
           View or Download PDF
        </a>
    </p>

</body>
</html>

##Create an S3 Bucket: Created an Amazon S3 bucket to store student study materials.
##Upload Study Materials: Uploaded PDF documents and images to the S3 bucket.
##Add S3 Links to Website: Added links to the uploaded study materials inside the HTML page.
##Create Target Group: Created an EC2 target group and registered both EC2 instances.
##Create Application Load Balancer: Configured an Application Load Balancer to receive incoming website traffic.
##Connect EC2 Instances with Load Balancer: Attached the target group to the Application Load Balancer and verified instance health.
##Test Application: Accessed the website using the Load Balancer DNS name and verified the study material links.

# Expected Output
##Student Notes Portal website accessible through the Load Balancer DNS.
##Website hosted on two EC2 instances.
##Study materials stored in Amazon S3.
##PDF and image links accessible from the website.
##Traffic distributed through the Application Load Balancer.

#Project Screenshots
##Screenshots of the implementation are available in the screenshots folder.

#Key Learnings
##Launching and configuring EC2 instances.
##Installing Apache on Linux.
##Creating and configuring S3 buckets.
##Uploading and accessing objects in S3.
##Configuring Target Groups.
##Creating an Application Load Balancer.
##Deploying a web application using AWS services.
